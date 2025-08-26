# Steps to generate the merged docx

- Step 1. Convert the HTML to Word using pandoc:

```sh
pandoc -f html -s .\ED-shex-semantics-20250611.labrify.html --reference-doc=custom.docx -t docx -o ED-shex-semantics-20250611_custom.docx
```

- Step 2: Copy/paste from section Overview of `merged.docx`.

- Step 3: Search and replace the 3 Heading styles using word. Search and replace Ctrl-H (click on format -> styles)
- "Heading 2" -> "IEEEStds Level 1 Header"
- "Heading 3" -> "IEEEStds Level 2 Header"
- "Heading 4" -> "IEEEStds Level 3 Header"
