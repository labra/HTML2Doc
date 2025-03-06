# Generate Word from HTML

Step 1. Create teh body of the spec from the index.html. It generates file `result.docx`

```sh
pandoc -f html -s index.html --reference-doc=custom-reference.docx -t docx -o result.docx
```

Step 2. Merge the `Intro.docx` and the previoux file to obtain the final `output.docx`:

```sh
../utils/docxmerge -i Intro.docx result.docx
```

## Customization

- To change styles in the body, we should change the file `custom.reference.docx`
- To change the content of the Intro we should change `Intro.docx`
- To change the content in the body, change `index.html`
