# api documentation for  [gulp-protractor (v4.1.0)](https://github.com/mllrsohn/gulp-protractor)  [![npm package](https://img.shields.io/npm/v/npmdoc-gulp-protractor.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-gulp-protractor) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-gulp-protractor.svg)](https://travis-ci.org/npmdoc/node-npmdoc-gulp-protractor)
#### A helper for protactor and gulp

[![NPM](https://nodei.co/npm/gulp-protractor.png?downloads=true)](https://www.npmjs.com/package/gulp-protractor)

[![apidoc](https://npmdoc.github.io/node-npmdoc-gulp-protractor/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-gulp-protractor_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-gulp-protractor/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-gulp-protractor/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-gulp-protractor/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Steffen Müller",
        "url": "https://github.com/steffenmllr"
    },
    "bugs": {
        "url": "https://github.com/mllrsohn/gulp-protractor/issues"
    },
    "contributors": [
        {
            "name": "Robbin Habermehl",
            "email": "robbin@habermehl.net"
        },
        {
            "name": "Rahul Raut",
            "email": "rahul@raut.me",
            "url": "https://github.com/rahulmr"
        }
    ],
    "dependencies": {
        "async": "^2.1.5",
        "dargs": "^5.1.0",
        "event-stream": "~3.3.0",
        "gulp-util": ">=2.2.14 <4.0.0",
        "protractor": "^5"
    },
    "description": "A helper for protactor and gulp",
    "devDependencies": {
        "expect.js": "~0.3.1",
        "jasmine": "^2.5.3",
        "mocha": "^3.2.0",
        "rewire": "^2.5.1",
        "sinon": "^1.17.3"
    },
    "directories": {},
    "dist": {
        "shasum": "be6589d4a35aa3a4daecd4cee8fe468aba08a8ad",
        "tarball": "https://registry.npmjs.org/gulp-protractor/-/gulp-protractor-4.1.0.tgz"
    },
    "engines": {
        "node": ">=4.2.0",
        "npm": ">=1.2.10"
    },
    "gitHead": "714f642d81e637635c6529ae839764bf820627db",
    "homepage": "https://github.com/mllrsohn/gulp-protractor",
    "keywords": [
        "gulpfriendly",
        "protractor"
    ],
    "license": "MIT",
    "main": "./index.js",
    "maintainers": [
        {
            "name": "mattfritz",
            "email": "mfritzer@gmail.com"
        },
        {
            "name": "rahulmr",
            "email": "rahulmraut@gmail.com"
        },
        {
            "name": "robbinhabermehl",
            "email": "robbin@habermehl.net"
        },
        {
            "name": "steffen",
            "email": "steffen@mllrsohn.com"
        }
    ],
    "name": "gulp-protractor",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/mllrsohn/gulp-protractor.git"
    },
    "scripts": {
        "test": "mocha",
        "wd:update": "webdriver-manager update"
    },
    "version": "4.1.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module gulp-protractor](#apidoc.module.gulp-protractor)
1.  [function <span class="apidocSignatureSpan">gulp-protractor.</span>getProtractorCli ()](#apidoc.element.gulp-protractor.getProtractorCli)
1.  [function <span class="apidocSignatureSpan">gulp-protractor.</span>getProtractorDir ()](#apidoc.element.gulp-protractor.getProtractorDir)
1.  [function <span class="apidocSignatureSpan">gulp-protractor.</span>protractor (options)](#apidoc.element.gulp-protractor.protractor)
1.  [function <span class="apidocSignatureSpan">gulp-protractor.</span>webdriver_standalone (cb)](#apidoc.element.gulp-protractor.webdriver_standalone)
1.  [function <span class="apidocSignatureSpan">gulp-protractor.</span>webdriver_update (opts, cb)](#apidoc.element.gulp-protractor.webdriver_update)
1.  [function <span class="apidocSignatureSpan">gulp-protractor.</span>webdriver_update_specific (opts)](#apidoc.element.gulp-protractor.webdriver_update_specific)



# <a name="apidoc.module.gulp-protractor"></a>[module gulp-protractor](#apidoc.module.gulp-protractor)

#### <a name="apidoc.element.gulp-protractor.getProtractorCli"></a>[function <span class="apidocSignatureSpan">gulp-protractor.</span>getProtractorCli ()](#apidoc.element.gulp-protractor.getProtractorCli)
- description and source-code
```javascript
function getProtractorCli() {
	var result = require.resolve('protractor');
	if (result) {
		return result.replace('index', 'cli');
	} else {
		throw new Error('Please check whether protractor is installed or not.');
	}
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gulp-protractor.getProtractorDir"></a>[function <span class="apidocSignatureSpan">gulp-protractor.</span>getProtractorDir ()](#apidoc.element.gulp-protractor.getProtractorDir)
- description and source-code
```javascript
function getProtractorDir() {
	if (protractorDir) {
		return protractorDir;
	}
	var result = require.resolve('protractor');
	if (result) {
		// console.log(result);
		// result is now something like
		// c:\\Source\\gulp-protractor\\node_modules\\protractor\\built\\index.js
		protractorDir = path.resolve(path.join(path.dirname(result), '..', '..', '.bin'));
		return protractorDir;
	}
	throw new Error('No protractor installation found.');
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gulp-protractor.protractor"></a>[function <span class="apidocSignatureSpan">gulp-protractor.</span>protractor (options)](#apidoc.element.gulp-protractor.protractor)
- description and source-code
```javascript
protractor = function (options) {
	var files = [],
		child, args;

	options = options || {};
	args = options.args || [];

	return es.through(function(file) {
		files.push(file.path);
		this.push(file);
	}, function() {
		var stream = this;

		// Enable debug mode
		if (options.debug) {
			args.push('debug');
		}

		// Attach Files, if any
		if (files.length) {
			args.push('--specs');
			args.push(files.join(','));
		}

		// Pass in the config file
		if (options.configFile) {
			args.unshift(options.configFile);
		}

		// console.log(getProtractorCli());

		// child = childProcess.spawn(path.resolve(getProtractorDir() + '/protractor'), args, {
		child = childProcess.fork(getProtractorCli(), args, {
			stdio: 'inherit',
			env: process.env
		}).on('exit', function(code) {
			if (child) {
				child.kill();
			}
			if (stream) {
				if (code) {
					stream.emit('error', new PluginError('gulp-protractor', 'protractor exited with code ' + code));
				} else {
					stream.emit('end');
				}
			}
		});
	});
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gulp-protractor.webdriver_standalone"></a>[function <span class="apidocSignatureSpan">gulp-protractor.</span>webdriver_standalone (cb)](#apidoc.element.gulp-protractor.webdriver_standalone)
- description and source-code
```javascript
webdriver_standalone = function (cb) {
	childProcess.spawn(path.resolve(getProtractorDir() + '/webdriver-manager' + winExt), ['start'], {
		stdio: 'inherit'
	}).once('close', cb);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gulp-protractor.webdriver_update"></a>[function <span class="apidocSignatureSpan">gulp-protractor.</span>webdriver_update (opts, cb)](#apidoc.element.gulp-protractor.webdriver_update)
- description and source-code
```javascript
webdriver_update = function (opts, cb) {
	var callback = (cb ? cb : opts);
	var options = (cb ? opts : null);
	var args = ['update', '--standalone'];
	if (options) {
		if (options.webdriverManagerArgs) {
			options.webdriverManagerArgs.forEach(function(element) {
				args.push(element);
			});
		}
		if (options.browsers) {
			options.browsers.forEach(function(element) {
				args.push('--' + element);
			});
		}
	}
	childProcess.spawn(path.resolve(getProtractorDir() + '/webdriver-manager' + winExt), args, {
		stdio: 'inherit'
	}).once('close', callback);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gulp-protractor.webdriver_update_specific"></a>[function <span class="apidocSignatureSpan">gulp-protractor.</span>webdriver_update_specific (opts)](#apidoc.element.gulp-protractor.webdriver_update_specific)
- description and source-code
```javascript
webdriver_update_specific = function (opts) {
	return wdUpdate.bind(this, opts);
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
