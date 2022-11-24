# Changelog

All notable changes to this project will be documented in this file. See [standard-version](https://github.com/conventional-changelog/standard-version) for commit guidelines.

## 6.0.0 (2022-11-24)


### ⚠ BREAKING CHANGES

* minimum supported `Node.js` version is `14.15.0`
* minimum supported `Node.js` version is `12.13.0`
* minimum supported webpack version is `5`
* This commit introduces a major refactoring of the loader.

- Remove node 0.10 and node 0.12 support
- The loaded module must now export a function
- This function will be called with the loader options
- This function must return an object with this structure

Property | Type | Description
:--------|:-----|:-----------
`code`   | `string|Buffer` | **Required**. The code that is passed to the next loader or to webpack.
`sourceMap` | [`SourceMap`](https://docs.google.com/document/d/1U1RGAehQwRypUTovF1KRlpiOFze0b-_2gc6fAH0KY0k/edit) | **Optional**. Will be pased to the next loader or to webpack.
`ast` | `any` | **Optional**. An [Abstract Syntax Tree](https://en.wikipedia.org/wiki/Abstract_syntax_tree) that will be passed to the next loader. Useful to speed up the build time if the next loader uses the same AST.
`dependencies` | `Array<string>` | **Default: `[]`**. An array of absolute, native paths to file dependencies that need to be watched for changes. 
`cacheable` | `boolean` | **Default: `false`**. Flag whether the code can be re-used in watch mode if none of the `dependencies` have changed.

- The function may also return a promise for async results
- Switch tooling to webpack-defaults

### Features

* add support for `contextDependencies` in the `{Object}` interface (`options.contextDependencies`) ([#23](https://github.com/GreenDou/ts-val-loader/issues/23)) ([78aa6fe](https://github.com/GreenDou/ts-val-loader/commit/78aa6fe0aaade187cc3dd2b8fd0449c9fd819e1c))
* added the `buildDependensies` option ([#63](https://github.com/GreenDou/ts-val-loader/issues/63)) ([04be3eb](https://github.com/GreenDou/ts-val-loader/commit/04be3ebd9515358929c661b3c9db98ba3d870ac1))
* added the `executableFile` option ([#65](https://github.com/GreenDou/ts-val-loader/issues/65)) ([b46090f](https://github.com/GreenDou/ts-val-loader/commit/b46090f323e3d2dcd75cbd552bd9447f98fd63e8))
* change expected module API ([caf2aab](https://github.com/GreenDou/ts-val-loader/commit/caf2aab538ec65c8cb47757863f4bbc1d5bf7e4d)), closes [#11](https://github.com/GreenDou/ts-val-loader/issues/11)
* pass `loaderContext` as 2nd parameter ([#47](https://github.com/GreenDou/ts-val-loader/issues/47)) ([cd5dd47](https://github.com/GreenDou/ts-val-loader/commit/cd5dd471f41dc5dbb541e09ea8af0f3ed0ad23de))
* support ECMA modules for the `executableFile` option ([#66](https://github.com/GreenDou/ts-val-loader/issues/66)) ([1e6675f](https://github.com/GreenDou/ts-val-loader/commit/1e6675fdf325c0973b1314fa3ad7984eaba197b9))
* support typescript ([8b727e4](https://github.com/GreenDou/ts-val-loader/commit/8b727e435396882341661c47b64e8a8a7cce7f02))


### Bug Fixes

* **.babelrc:** enable modules ([b0b116a](https://github.com/GreenDou/ts-val-loader/commit/b0b116a38d94ec5ef6dcdb4d1c0928268043696b))
* add support `webpack@4` ([#30](https://github.com/GreenDou/ts-val-loader/issues/30)) ([fea518d](https://github.com/GreenDou/ts-val-loader/commit/fea518d90d4619ce41e84445e897cda210086302))
* **getOptions:** deprecation warn in loaderUtils ([#10](https://github.com/GreenDou/ts-val-loader/issues/10)) ([d2db561](https://github.com/GreenDou/ts-val-loader/commit/d2db5618a97d89c74d2db950fc8085ba7ab78d8b))
* link on package ([#44](https://github.com/GreenDou/ts-val-loader/issues/44)) ([f234364](https://github.com/GreenDou/ts-val-loader/commit/f234364a0c98f05fd0c4203c0a3946d6f0075adc))
* **src:** add CJS wrapper ([cd043f5](https://github.com/GreenDou/ts-val-loader/commit/cd043f5d3f0f55cda3cc37b288ab05d51c275703))


* drop node v12 ([#97](https://github.com/GreenDou/ts-val-loader/issues/97)) ([6b96e4d](https://github.com/GreenDou/ts-val-loader/commit/6b96e4d3a807663299553d92840aecc90438d9f9))
* next ([#61](https://github.com/GreenDou/ts-val-loader/issues/61)) ([145fc71](https://github.com/GreenDou/ts-val-loader/commit/145fc7132bc5eb09792d7a8c8fe8efa7275b08dc))
* node 10 dropped ([#67](https://github.com/GreenDou/ts-val-loader/issues/67)) ([c7cca46](https://github.com/GreenDou/ts-val-loader/commit/c7cca46897db7bd90c552c5b41260ac2d97ba5e7))

## [5.0.0](https://github.com/webpack-contrib/val-loader/compare/v4.0.0...v5.0.0) (2022-05-17)


### ⚠ BREAKING CHANGES

* minimum supported `Node.js` version is `14.15.0`

## [4.0.0](https://github.com/webpack-contrib/val-loader/compare/v3.1.0...v4.0.0) (2021-05-14)


### ⚠ BREAKING CHANGES

* minimum supported `Node.js` version is `12.13.0`

## [3.1.0](https://github.com/webpack-contrib/val-loader/compare/v3.0.0...v3.1.0) (2021-03-01)


### Features

* added the `buildDependensies` option ([#63](https://github.com/webpack-contrib/val-loader/issues/63)) ([04be3eb](https://github.com/webpack-contrib/val-loader/commit/04be3ebd9515358929c661b3c9db98ba3d870ac1))
* added the `executableFile` option ([#65](https://github.com/webpack-contrib/val-loader/issues/65)) ([b46090f](https://github.com/webpack-contrib/val-loader/commit/b46090f323e3d2dcd75cbd552bd9447f98fd63e8))
* support ECMA modules for the `executableFile` option ([#66](https://github.com/webpack-contrib/val-loader/issues/66)) ([1e6675f](https://github.com/webpack-contrib/val-loader/commit/1e6675fdf325c0973b1314fa3ad7984eaba197b9))

## [3.0.0](https://github.com/webpack-contrib/val-loader/compare/v2.1.2...v3.0.0) (2020-12-22)


### ⚠ BREAKING CHANGES

* minimum supported webpack version is `5`

### [2.1.2](https://github.com/webpack-contrib/val-loader/compare/v2.1.1...v2.1.2) (2020-10-09)

### Chore

* update `schema-utils`

### [2.1.1](https://github.com/webpack-contrib/val-loader/compare/v2.1.0...v2.1.1) (2020-04-09)

### Chore

* update deps

## [2.1.0](https://github.com/webpack-contrib/val-loader/compare/v2.0.2...v2.1.0) (2019-12-17)


### Features

* pass `loaderContext` as 2nd parameter ([#47](https://github.com/webpack-contrib/val-loader/issues/47)) ([cd5dd47](https://github.com/webpack-contrib/val-loader/commit/cd5dd471f41dc5dbb541e09ea8af0f3ed0ad23de))

### [2.0.2](https://github.com/webpack-contrib/val-loader/compare/v2.0.1...v2.0.2) (2019-11-25)


### Chore

* add the `funding` field in `package.json`



### [2.0.1](https://github.com/webpack-contrib/val-loader/compare/v2.0.0...v2.0.1) (2019-11-19)


### Bug Fixes

* link on package ([#44](https://github.com/webpack-contrib/val-loader/issues/44)) ([f234364](https://github.com/webpack-contrib/val-loader/commit/f234364a0c98f05fd0c4203c0a3946d6f0075adc))

### [2.0.0](https://github.com/webpack-contrib/val-loader/compare/v1.1.1...v2.0.0) (2019-11-14)


### Bug Fixes

* support `webpack@5`


### Features

* better handle errors from a module
* pass `module.parent` to a module
* validate loader options


### BREAKING CHANGES

* minimum supported node version is `10.13.0`
* minimum supported webpack version is `4.0.0`



<a name="1.1.1"></a>
## [1.1.1](https://github.com/webpack-contrib/val-loader/compare/v1.1.0...v1.1.1) (2018-06-21)


### Bug Fixes

* add support for `webpack@4` ([#30](https://github.com/webpack-contrib/val-loader/issues/30)) ([fea518d](https://github.com/webpack-contrib/val-loader/commit/fea518d))



<a name="1.1.0"></a>
# [1.1.0](https://github.com/webpack-contrib/val-loader/compare/v1.0.2...v1.1.0) (2017-11-19)


### Features

* add support for `contextDependencies` in the `{Object}` interface (`options.contextDependencies`) ([#23](https://github.com/webpack-contrib/val-loader/issues/23)) ([78aa6fe](https://github.com/webpack-contrib/val-loader/commit/78aa6fe))



<a name="1.0.2"></a>
## [1.0.2](https://github.com/webpack-contrib/val-loader/compare/v1.0.1...v1.0.2) (2017-03-21)


### Bug Fixes

* **.babelrc:** enable modules ([b0b116a](https://github.com/webpack-contrib/val-loader/commit/b0b116a))



<a name="1.0.1"></a>
## [1.0.1](https://github.com/webpack-contrib/val-loader/compare/v1.0.0...v1.0.1) (2017-03-20)


### Bug Fixes

* **src:** add CJS wrapper ([cd043f5](https://github.com/webpack-contrib/val-loader/commit/cd043f5))



<a name="1.0.0"></a>
# [1.0.0](https://github.com/webpack-contrib/val-loader/compare/v0.5.1...v1.0.0) (2017-03-16)


### Features

* change expected module API ([caf2aab](https://github.com/webpack-contrib/val-loader/commit/caf2aab))


### BREAKING CHANGES

* this commit introduces a major refactoring of the loader.
* remove node 0.10 and node 0.12 support
* the loaded module must now export a function
* this function will be called with the loader options
* this function must return an object with this structure

Property | Type | Description
:--------|:-----|:-----------
`code`   | `string|Buffer` | **Required**. The code that is passed to the next loader or to webpack.
`sourceMap` | [`SourceMap`](https://docs.google.com/document/d/1U1RGAehQwRypUTovF1KRlpiOFze0b-_2gc6fAH0KY0k/edit) | **Optional**. Will be pased to the next loader or to webpack.
`ast` | `any` | **Optional**. An [Abstract Syntax Tree](https://en.wikipedia.org/wiki/Abstract_syntax_tree) that will be passed to the next loader. Useful to speed up the build time if the next loader uses the same AST.
`dependencies` | `Array<string>` | **Default: `[]`**. An array of absolute, native paths to file dependencies that need to be watched for changes.
`cacheable` | `boolean` | **Default: `false`**. Flag whether the code can be re-used in watch mode if none of the `dependencies` have changed.

* the function may also return a promise for async results
* switch tooling to webpack-defaults
