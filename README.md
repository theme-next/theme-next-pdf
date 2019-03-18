<h1 align="center"><a href="https://github.com/mozilla/pdf.js">PDF.js</a> for <a href="https://github.com/theme-next">NexT</a></h1>

<h2 align="center">Introduce</h2>

This is a plugin that allows to preview PDF files in the blog pages.

It's based on PDFObject and PDF.js. If the browser supports embedded PDFs natively, PDFObject will create a `<embed>` tag and include the PDF file on your website. Otherwise it will create a `<iframe>` tag and uses PDF.js to render the pdf file.

Follow the guide below to install dependencies.

<h1 align="center">Installation</h1>

<h2 align="center">Step 1 &rarr; Go to NexT dir</h2>

Change dir to **NexT** directory. There must be `layout`, `source`, `languages` and other directories:

```sh
$ cd themes/next
$ ls
bower.json  _config.yml  docs  gulpfile.coffee  languages  layout  LICENSE.md  package.json  README.md  scripts  source  test
```

<h2 align="center">Step 2 &rarr; Get module</h2>

Install module to `source/lib` directory:

```sh
$ git clone https://github.com/theme-next/theme-next-pdf source/lib/pdf
```

<h2 align="center">Step 3 &rarr; Set it up</h2>

Enable module in **NexT** `_config.yml` file:

```yml
# PDF tag, requires two plugins: pdfObject and pdf.js
# pdfObject will try to load pdf files natively, if failed, pdf.js will be used.
# The following `cdn` setting is only for pdfObject, because cdn for pdf.js might be blocked by CORS policy.
# So, YOU MUST install the dependency of pdf.js if you want to use pdf tag and make it work on all browsers.
# See: https://github.com/theme-next/theme-next-pdf
pdf:
  enable: true
  # Default height
  height: 500px
  pdfobject:
    # Use 2.1.1 as default, jsdelivr as default CDN, works everywhere even in China
    cdn: //cdn.jsdelivr.net/npm/pdfobject@2.1.1/pdfobject.min.js
    # CDNJS, provided by cloudflare, maybe the best CDN, but not works in China
    #cdn: //cdnjs.cloudflare.com/ajax/libs/pdfobject/2.1.1/pdfobject.min.js
```

<h1 align="center">Usage</h1>
In order to embed PDF files in the article, you just need to create an `pdf` tag with the URL of your local PDF file, e.g.

```
{% pdf /path/to/your/file.pdf %}
```
Notice: Do not use cross-origin PDF files, it might be blocked by the CORS policy.

Enjoy it!

<h1 align="center">Update</h1>

```sh
$ cd themes/next/source/lib/pdf
$ git pull
```
