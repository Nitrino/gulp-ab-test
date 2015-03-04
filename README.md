#gulp-ab-test

##Usage
````js
  gulp.task('ab-test', function() {
  gulp.src('./app/**/*.*')
    .pipe(abTest({context: { TEST: gulp.env.test}}))
    .pipe(gulp.dest('./ab_test/'))
});
````
````bash
gulp watch --test=A
````
