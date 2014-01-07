# gulp-scaffold

> Use Gulp to scaffold things.

This is not a Gulp plugin, just an instruction and some examples on how to scaffold all the things with Gulp.

## How To Scaffold Things

This very simple pattern parses cli options with @substack's optimist module and hands them right over to gulp-template as an object.

```js
gulp.task('default', function () {
  gulp.src('some/template-file.xx')
    .pipe(template(require('optimist').argv))
    .pipe(gulp.dest('some/destination'));
});
```

## Get started

Clone this repo:

```sh
git clone http://github.com/distilledhype/gulp-scaffold
```

Then install all the dendencies with 

```js
npm install 
```

Now you can go ahead and scaffold READMEs:

```js
// Scaffold a README.md.
// `gulp readme --headline="My Headline" --description="Some description."`
gulp.task('readme', function () {
  gulp.src('templates/README.md')
    .pipe(template(argv))
    .pipe(gulp.dest('results/readme'));
});
```

Or JavaScript modules:

```js
// Scaffold a JavaScript module.
// `gulp module --name="moduleName"`
gulp.task('plugin', function() {
	gulp.src('templates/module.js')
		.pipe(template(argv))
		.pipe(gulp.dest('results/module/' + argv.name.toLowerCase() + '.js'));
});
```

Or anything you want, really.
