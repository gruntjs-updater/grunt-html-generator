# grunt-html-generator

> Grunt task to generate html files.

## Getting Started
This plugin requires Grunt `~0.4.1`

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. Once you're familiar with that process, you may install this plugin with this command:

```shell
npm install grunt-html-generator --save-dev
```

Once the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```js
grunt.loadNpmTasks('grunt-html-generator');
```

## The "html-generator" task

### Overview
In your project's Gruntfile, add a section named `html-generator` to the data object passed into `grunt.initConfig()`.

```js
grunt.initConfig({
  "html-generator": {
    options: {
      root: ".",
      html: "html"
    },
    target: {
      files: {
        "./output-file.html": {
          js: [ "js/lib/*.js", "js/*.js" ],
          css: "css/css/*.css",
          title: "<% pkg.name %>",
          head: "head",
          body: "body"
        },
      },
    },
  },
})
```

The above code create a html document named "output-file.html" with the content bellow.

```html
<!DOCTYPE html>
<html>
<head>
	<title>grunt-html-generator</title>
	<!-- ./www/html/head.html -->
	<link type="text/css" rel="stylesheet" href="css/a.css" />
	<link type="text/css" rel="stylesheet" href="css/b.css" />
	<link type="text/css" rel="stylesheet" href="css/c.css" />
	<script type="text/javascript" src="js/lib/a.js" />
	<script type="text/javascript" src="js/lib/b.js" />
	<script type="text/javascript" src="js/lib/c.js" />
	<script type="text/javascript" src="js/a.js" />
	<script type="text/javascript" src="js/b.js" />
	<script type="text/javascript" src="js/c.js" />
</head>
<body>
	<h1>./www/html/body.html</h1>
</body>
</html>
```