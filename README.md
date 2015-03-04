#gulp-ab-test

##Usage
````js
  var abTest = require('gulp-ab-test');


  gulp.task('ab-test', function() {
  gulp.src('./app/**/*.*')
    .pipe(abTest({context: { TEST: gulp.env.test}}))
    .pipe(gulp.dest('./ab_test/'))
});
````
````bash
gulp watch --test=A
````
`main.styl`
````stylus
// @if TEST='A'
float left
// @endif

// @if TEST='B'
float right
// @endif
````
