#gulp-tachi
> product improvement  
> as manufacturing samurai sword  
> required years

Allows conveniently split up your code for AB testing

##Usage

````js
  var abTest = require('gulp-tachi');


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
