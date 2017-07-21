# gulp-debug [![Build Status](https://travis-ci.org/jmquigley/gulp-debug.svg?branch=master)](https://travis-ci.org/jmquigley/gulp-debug)

> Debug [Vinyl](https://github.com/gulpjs/vinyl) file streams to see what files are run through your Gulp pipeline

<img src="screenshot.png" width="415">


## Install

```
$ npm install --save-dev gulp-debug
```


## Usage

```js
const gulp = require('gulp');
const debug = require('gulp-debug');

gulp.task('default', () => {
	return gulp.src('foo.js')
		.pipe(debug({log: console.log, title: 'unicorn:'}))
		.pipe(gulp.dest('dist'));
});
```

## API

### debug([options])

#### options

##### title

Type: `string`<br>
Default: `gulp-debug:`

Give it a custom title so it's possible to distinguish the output of multiple instances logging at once.

##### minimal

Type: `boolean`<br>
Default: `true`

By default only relative paths are shown. Turn off minimal mode to also show `cwd`, `base`, `path`.

The [`stat` property](http://nodejs.org/api/fs.html#fs_class_fs_stats) will be shown when you run gulp in verbose mode: `gulp --verbose`.

##### log

Type: `object`
Default: `gutil.log`

By default the output is sent to `gutil.log`.  With this option the logging facility can be overriden to use another logger (such as `console.log`).

##### showFiles

Type: `boolean`<br>
Default: `true`

Setting this to false will skip printing the file names and only show the file count.


## License

MIT © [Sindre Sorhus](https://sindresorhus.com)
