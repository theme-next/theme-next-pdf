<h1 align="center"><a href="https://github.com/mozilla/pdf.js">PDF.js</a> for <a href="https://github.com/theme-next">NexT</a></h1>

<h2 align="center">Introduce</h2>

This is a plugin that allows to preview PDF files in the blog pages.

It's based on PDFObject and PDF.js. If the browser supports embedded PDFs natively, PDFObject will create a `<embed>` tag and include the PDF file on your website. Otherwise it will create a `<iframe>` tag and uses PDF.js to render the pdf file.

Follow the guide below to install dependencies, then edit `_config.yml`:
```
pdf:
  enable: true
```
<h3 align="center">Usage</h3>
You just need to create an inline link point to your local pdf file, e.g.

```
[](/path/to/your/file.pdf)
```
Notice: Do not use cross-origin pdf files, it might be blocked by the CORS policy.

Enjoy it!

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
# PDF Support
pdf:
  enable: true

  # Default(true) will load PDFObject/PDF.js script on demand
  # That is it only render those page who has 'pdf: true' in Front Matter.
  # If you set it to false, it will load PDFObject/PDF.js srcipt EVERY PAGE.
  per_page: true

  height: 500px

  pdfobject:
    # Use 2.1.1 as default, cloudflare as default CDN
    cdn: //cdnjs.cloudflare.com/ajax/libs/pdfobject/2.1.1/pdfobject.min.js
```

<h1 align="center">Update</h1>

```sh
$ cd themes/next/source/lib/pdf
$ git pull
```
