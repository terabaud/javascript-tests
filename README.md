# javascript-tests
A comparison of test frameworks in javascript

In this repo, I am going to experiment with several test frameworks that are available in JavaScript and give a quick overview.

On my machine, I am using the current LTS version of node in a Windows environment, but other platforms with node versions >= v8.11.3 should work fine. 

For bundling and transpilation, I'm using `babel` and the [parceljs bundler](https://parceljs.org).

## running the example

Type `npm install` to install the dependencies and then type `npm start`.
Alternatively, you can also just browse to https://terabaud.github.io/javascript-tests/ and hit F12.

## What are we going to test?

For now, we are going to test a pretty boring [math.js](https://github.com/terabaud/javascript-tests/blob/master/src/math.js) library.
As a pretest step, linting is done via  [standardjs](https://standardjs.com).

## Testing

Type `npm test` to run all the tests.

### tape

[tape](https://github.com/substack/tape) is a simple testing framework that produces [TAP](http://testanything.org/) output, a standardized protocol for automated tests. 

To use tape in your project, install [tape](https://npmjs.com/package/tape), [babel-tape-runner](https://npmjs.com/package/babel-tape-runner) alongside with  [babel-preset-env](https://npmjs.com/package/babel-preset-env) or any other babel preset you like. To beautify the output, [faucet](https://github.com/substack/faucet) is used.

No other configuration is needed.

### mocha and chai

[mocha](https://mochajs.org) is a commonly used testing framework for node and in the browser. It is often used in combination with [chai](https://chaijs.com), a BDD/TDD assertion library.

To add mocha into your project, `npm install mocha chai babel-register --save-dev` and call the tests via `mocha --require babel-register`. The require parameter is needed for ES6+ support. If you don't specify a file, mocha executes everything inside the `test` folder.

### Jest

[jest](http://jestjs.io/) by facebook features zero (minimal) configuration, test parallelization and built-in code coverage reports.

### Other testing frameworks and tools (not covered here)

* [Enzyme](https://github.com/airbnb/enzyme) by airbnb is a set of testing utilities for React applications and can be used by any common testing framework.
* [jasmine](https://jasmine.github.io/), a BDD testing framework by Pivotal Labs.
* [ShouldJS](https://shouldjs.github.io) is another assertion library and very similar to chai.
