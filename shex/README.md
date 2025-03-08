# Generate Word from HTML

## Requirements

- [single-file](https://www.npmjs.com/package/single-file-cli): I installed if with npm.
- [pandoc](https://pandoc.org/): I installed locally [pandoc](https://pandoc.org/).
- [DocxMerge](https://github.com/jamessantiago/DocxMerge): merges docx files. I downloaded to the folder `utils` as a Windows binary. I googled for another tool that could merge two `.docx` files but I didn't find it. As this is a `.exe`, I suspect, this will only work on Windows...

## Conversion instructions

Step 1. Create the cooked.html file which is what is obtained after running javascript + CSS on the index.html file.

I ran it from Windows (where I have chrome.exe and single-file installed), when I was in the `shexSpec/spec` folder.

```sh
npx single-file index.html --dump-content > \src\word\HTML2Doc\shex\cooked.html
```

Step 2. Create the body of the spec from the index.html. It generates file `result.docx`

```sh
pandoc -f html -s cooked.html --reference-doc=custom.docx -t docx -o body.docx
```

Step 3. Merge the `Intro.docx` and the previoux file (`body.docx`) to obtain the final `draft-merged.docx`:

```sh
../utils/docxmerge -i Intro.docx body.docx -o merged.docx
```

This generates `merged.docx` which contains the merge of the documents.

## Customizations

- To change styles in the body, we should change the file `custom.docx`
- To change the content of the Intro we should change `Intro.docx`
- To change the content in the body, change `index.html`
- Some parts of the body are generated from `respec-ieee.js`

## Some problems to solve

- Some of the text in Intro.docx still needs to be defined...
