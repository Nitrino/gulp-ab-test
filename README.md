#gulp-tachi
> product improvement  
> as manufacturing samurai sword  
> required years

Allows conveniently split up your code for AB testing

##Usage

Install:

`npm install --save gulp-tachi`

Gulpfile:

````js
  var abTest = require('gulp-tachi');


  gulp.task('ab-test', function() {
  gulp.src('./app/**/*.*')
    .pipe(abTest({context: { TEST: gulp.env.test}}))
    .pipe(gulp.dest('./ab_test/'))
});
````

Run:

````bash
gulp watch --test=A
````

##Examples:
###`main.styl`

source:
````stylus
// @if TEST='A'
float left
// @endif

// @if TEST='B'
float right
// @endif
````

Run:
`gulp watch --test=A`

compile:
````stylus
float left
````

###`index.html`

source:
````html
<head>
  <title>
    <!-- @if TEST='A' -->
      Tittle for A test
    <!-- @endif -->

    <!-- @if TEST='B' -->
      Tittle for B test
    <!-- @endif -->
  </title>
</head>
````

Run:
`gulp watch --test=B`

compile:
````html
<head>
  <title>
    Tittle for B test
  </title>
</head>
````
