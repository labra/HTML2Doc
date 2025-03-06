# Generate Word from HTML

## Requirements

I installed locally [pandoc](https://pandoc.org/).

I use the DocxMerge tool which I downloaded to the folder `utils` as a Windows binary. I googled for another tool that could merge two `.docx` files but I didn't find it. As this is a `.exe`, I suspect, this will only work on Windows...

## Conversion instructions

Step 1. Create teh body of the spec from the index.html. It generates file `result.docx`

```sh
pandoc -f html -s index.html --reference-doc=custom-reference.docx -t docx -o result.docx
```

Step 2. Merge the `Intro.docx` and the previoux file to obtain the final `output.docx`:

```sh
../utils/docxmerge -i Intro.docx result.docx -o final.docx
```

This generates `final.docx` which contains the merge of the documents.

## Customizations

- To change styles in the body, we should change the file `custom.reference.docx`
- To change the content of the Intro we should change `Intro.docx`
- To change the content in the body, change `index.html`

## Some problems to solve

- Some of the text in Intro.docx still needs to be defined...
- The references are still included like `[[!JSON-LD]]`
