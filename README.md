
![dependencies](https://img.shields.io/david/billybonks/ember-cli-stylelint.svg)
[![ember-observer](http://emberobserver.com/badges/ember-cli-stylelint.svg)](https://emberobserver.com/addons/ember-cli-stylelint)
[![downloads](https://img.shields.io/npm/dm/ember-cli-stylelint.svg)](https://www.npmjs.com/package/ember-cli-stylelint)
[![build](https://travis-ci.org/billybonks/ember-cli-stylelint.svg?branch=master)](https://travis-ci.org/billybonks/ember-cli-stylelint/branches)

Installation
------------------------------------------------------------------------------

# ember-cli-stylelint

An Ember-CLI addon that allows easy integration with [stylelint](http://stylelint.io/)

## Installation

`ember install ember-cli-stylelint`

## Syntax

**Non-standard syntaxes will be automatically inferred from file extensions.**

To force a specific syntax configure the option in your `ember-cli-build`:

```javascript
let app = new EmberApp(defaults, {
  stylelint: {
    linterConfig:{
      syntax: 'less'
    },
  }
});
```

You can use one of the following values for `syntax`:

`'css-in-js'|'html'|'less'|'markdown'|'sass'|'scss'|'sugarss'`

## Configuration

Linting configuration can be added in a

* a stylelint property in package.json
* a .stylelintrc file
* a stylelint.config.js file exporting a JS object

as required by [stylelint](http://stylelint.io/user-guide/configuration/).

the parent key is `styleLint`

## Options

`linterConfig` {Object}

Hash as specified by [stylelint](https://github.com/stylelint/stylelint/blob/master/docs/user-guide/node-api.md)

doesn't accept `files` option

`onError` {function}

A hook that allows you to do whatever you want

`consoleLogger` {function}

This function is called every time a file has an error. It allows you to generate custom error output according to your preferences.

`testFailingFiles` {boolean}

If true it will generate a unit test if the file fails lint.

`testPassingFiles` {boolean}

If true it will generate a unit test if the file passes lint.

`generateTests` {boolean}

If true it will generate tests for both passing and failing tests, overrides the testPassingFiles and testFailingFiles

`disableConsoleLogging` {boolean}

If true it will disable logging of errors to console

`includePaths` {array of strings}

Paths representing trees to lint. The app tree itself will always be included.
In an addon, that path is `tests/dummy/app/styles/` (by default). Addon authors
can set `includePaths: [ 'app/styles' ]` to also lint styles in `app/styles/`.

## Running Tests

* `npm test`

## Development

All tests are currently contained in tests/runner.js. This uses Mocha/Chai, not Ember Testing. Tests can be run with:

`npm test`

Contributing
------------------------------------------------------------------------------

See the [Contributing](CONTRIBUTING.md) guide for details.


License
------------------------------------------------------------------------------

PRs are welcomed and should be issued to the master branch.
