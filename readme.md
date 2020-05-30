### Resume

To build the PDF, run

```
docker run --rm -v ~/.fonts/:/usr/share/fonts/ -v `pwd`:/cv -w /cv pandoc/latex -s -f markdown-auto_identifiers+inline_code_attributes cv.md -o cv.pdf --template=template.tex --pdf-engine=xelatex
```
