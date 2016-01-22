# junit-report-merger

[![NPM version][npm-version-image]][npm-url] [![NPM downloads][npm-downloads-image]][npm-url] [![Dependencies][deps-image]][deps-url] [![Dev. Dependencies][dev-deps-image]][dev-deps-url] [![MIT License][license-image]][license-url] [![Build Status][travis-image]][travis-url]

Merges multiple JUnit XML reports into one.

JUnit XML reports are generated by reporters for popular testing frameworks, such as [`mocha-junit-reporter`](https://www.npmjs.com/package/mocha-junit-reporter) and [`karma-junit-reporter`](https://www.npmjs.com/package/karma-junit-reporter). Other packages also may store test results in JUnit XML format.

`junit-report-merger` creates a new test results report in JUnit XML format by collecting all `<testsuite>` elements from all XML reports and putting them together.

This can be useful when you have multiple test runners in your test pipeline but you need a single output file which includes results from all test runners.


## API

Package exports a single object with the following methods.

#### `mergeFiles(destFilePath:String, srcFilePaths:String, options:Object, cb:Function)`

Reads multiple files, merges their contents and write into the given file.
+ `destFilePath`_{String}_ - Where the output should be stored. Denotes a path to file. If file already exists, it will be overwritten.
+ `srcFilePaths`_{String[]}_ - Paths to the files which should be merged.
+ `options`_{Object}_ - Optional. Currently unused.
+ `cb`_{Function}_ - Callback function which will be called at completion. Will receive error as first argument if any.


#### `mergeStreams(destStream:WriteStream, srcStreams:ReadStream[], options:Object, cb:Function)`

Reads multiple streams, merges their contents and write into the given stream.
+ `destStream`_{WriteStream}_ - A stream which will be used to write the merge result.
+ `srcStreams`_{ReadStream[]}_ - Streams which will be used to read data from.
+ `options`_{Object}_ - Optional. Currently unused.
+ `cb`_{Function}_ - Callback function which will be called at completion. Will receive error as first argument if any.


#### `mergeToString(srcStrings:String[], options:Object):String`

Merges contents of given XML strings and returns resulting XML string.
+ `srcStrings`_{String[]}_ - Array of strings to merge together.
+ `options`_{Object}_ - Optional. Currently unused.
+ Returns string containing merge result.


## License

MIT (http://www.opensource.org/licenses/mit-license.php)

[deps-image]: https://img.shields.io/david/bhovhannes/junit-report-merger.svg
[deps-url]: https://david-dm.org/bhovhannes/junit-report-merger

[dev-deps-image]: https://img.shields.io/david/dev/bhovhannes/junit-report-merger.svg
[dev-deps-url]: https://david-dm.org/bhovhannes/junit-report-merger#info=devDependencies

[license-image]: http://img.shields.io/badge/license-MIT-blue.svg?style=flat
[license-url]: LICENSE

[npm-url]: https://www.npmjs.org/package/junit-report-merger
[npm-version-image]: https://img.shields.io/npm/v/junit-report-merger.svg?style=flat
[npm-downloads-image]: https://img.shields.io/npm/dm/junit-report-merger.svg?style=flat

[travis-url]: https://travis-ci.org/bhovhannes/junit-report-merger
[travis-image]: https://img.shields.io/travis/bhovhannes/junit-report-merger.svg?style=flat
