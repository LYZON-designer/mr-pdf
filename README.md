## 📌 Introduction

This is a PDF generator from document website such as `docusaurus`, `vuepress`, `mkdocs`.

## ⚡ Usage
```shell
npx mr-pdf --initialDocsUrl="https://example.com" --paginationSelector="li > a"
```

## 🍗 CLI Options

- `--initialDocsUrl`:               set url to start generating PDF from.

- `--paginationSelector`:  used to find next page to be printed for looping.

- `--excludeSelectors`: exclude selectors from PDF. Separate each selector **with comma and no space**. But you can use space in each selector. ex: `--excludeSelectors=".nav,.next > a"`

- `--cssStyle`: css style to adjust PDF output ex: `--cssStyle="body{padding-top: 0;}"` *If you're project owner you can use `@media print { }` to edit CSS for PDF.

- `--outputPDFFilename`:   name of the output PDF file. Default is `mr-pdf.pdf`.

- `--pdfMargin`: set margin around PDF file. Separate each margin **with comma and no space**. ex: `--pdfMargin="10,20,30,40"`. This sets margin `top: 10px, right: 20px, bottom: 30px, left: 40px`.

- `--pdfFormat`:            pdf format ex: `--pdfFormat="A3"`. Please check this link for available formats [Puppeteer document](https://pptr.dev/#?product=Puppeteer&version=v5.2.1&show=api-pagepdfoptions)


## 🎨 Examples and Demo PDF

### Docusaurus v1
https://docusaurus.io/en/

`initialDocsUrl`: https://docusaurus.io/docs/en/installation

`demoPDF`: https://drive.google.com/file/d/1HK5tBKmK0JBsFMNwoYRB9fDs9rkJhGRC/view?usp=sharing


`command`:
```shell
npx mr-pdf --initialDocsUrl="https://docusaurus.io/docs/en/installation" --paginationSelector=".docs-prevnext > a.docs-next" --excludeSelectors=".fixedHeaderContainer,footer.nav-footer,#docsNav,nav.onPageNav,a.edit-page-link,div.docs-prevnext" --cssStyle=".navPusher {padding-top: 0;}" --pdfMargin="20"
```

### Docusaurus v2 beta
https://docusaurus.io/

`initialDocsUrl`: https://docusaurus.io/docs

`demoPDF`:
https://drive.google.com/file/d/1Oh0VVHfoQTJ9gYVHQTuLUaXEGrhWZdXR/view?usp=sharing


`command`:
```shell
npx mr-pdf --initialDocsUrl="https://docusaurus.io/docs/" --paginationSelector=".pagination-nav__item--next > a" --excludeSelectors=".margin-vert--xl a"
```

### Vuepress
https://vuepress.vuejs.org/

`initialDocsUrl`:

https://vuepress.vuejs.org/guide/

`demoPDF`: https://drive.google.com/file/d/1v4EhFARPHPfYZWgx2mJsr5Y0op3LyV6u/view?usp=sharing

`command`:
```shell
npx mr-pdf --initialDocsUrl="https://vuepress.vuejs.org/guide/" --paginationSelector=".page-nav .next a" --excludeSelectors="header.navbar,aside.sidebar,footer.page-edit .edit-link,.global-ui,.page-nav"
```

### Mkdocs
https://www.mkdocs.org/

`initialDocsUrl`: https://www.mkdocs.org/

`demoPDF`: https://drive.google.com/file/d/1xVVDLmBzPQIbRs9V7Upq2S2QIjysS2-j/view?usp=sharing

`command`: 
```shell
npx mr-pdf --initialDocsUrl="https://www.mkdocs.org/" --paginationSelector="ul.navbar-nav li.nav-item a[rel~='next']" --excludeSelectors=".navbar.fixed-top,footer,.homepage .container .row .col-md-3,#toc-collapse" --cssStyle=".col-md-9 {flex: 0 0 100%; max-width: 100%;}"
```

### Material for mkdocs
https://squidfunk.github.io/mkdocs-material/


`initialDocsUrl`: https://squidfunk.github.io/mkdocs-material/getting-started/

`demoPDF`: https://drive.google.com/file/d/1oB5fyHIyZ83CUFO9d4VD4q4cJFgGlK-6/view?usp=sharing

`command`: 
```shell
npx mr-pdf --initialDocsUrl="https://squidfunk.github.io/mkdocs-material/getting-started/" --paginationSelector="a.md-footer-nav__link--next" --excludeSelectors="header.md-header,.announce,nav.md-tabs,.md-main__inner .md-sidebar--primary,.md-main__inner .md-sidebar--secondary,footer" --cssStyle=".md-content {max-width: 100%!important;}"
```


#### PR to add new docs is welcome here... 😸


## 📄 How this plugin works
This plugin uses [puppeteer](https://github.com/puppeteer/puppeteer) to make PDF of the document website.

![mr-pdf-diagram](https://user-images.githubusercontent.com/29557494/90359040-c8fb9780-e092-11ea-89c7-1868bc32919f.png)


## 🎉 Thanks
This repo's code is coming from https://github.com/KohheePeace/docusaurus-pdf.

Thanks for awesome code made by [@maxarndt](https://github.com/maxarndt) and [@aloisklink](https://github.com/aloisklink)
