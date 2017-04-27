# npmdoc-cookies

#### basic api documentation for  [cookies (v0.7.0)](https://github.com/pillarjs/cookies#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-cookies.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-cookies) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-cookies.svg)](https://travis-ci.org/npmdoc/node-npmdoc-cookies)

#### Cookies, optionally signed using Keygrip.

[![NPM](https://nodei.co/npm/cookies.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/cookies)

- [https://npmdoc.github.io/node-npmdoc-cookies/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-cookies/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-cookies/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-cookies/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-cookies/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-cookies/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Jed Schmidt",
        "url": "http://jed.is"
    },
    "bugs": {
        "url": "https://github.com/pillarjs/cookies/issues"
    },
    "contributors": [
        {
            "name": "Douglas Christopher Wilson"
        }
    ],
    "dependencies": {
        "depd": "~1.1.0",
        "keygrip": "~1.0.1"
    },
    "description": "Cookies, optionally signed using Keygrip.",
    "devDependencies": {
        "express": "4.9.8",
        "istanbul": "0.4.5",
        "mocha": "2.5.3",
        "restify": "2.8.1",
        "supertest": "1.1.0"
    },
    "directories": {},
    "dist": {
        "shasum": "0bc961d910c35254980fc7c9eff5da12011bbf00",
        "tarball": "https://registry.npmjs.org/cookies/-/cookies-0.7.0.tgz"
    },
    "engines": {
        "node": ">= 0.8"
    },
    "files": [
        "HISTORY.md",
        "LICENSE",
        "README.md",
        "index.js"
    ],
    "gitHead": "c582e55ef687d869ddfb50fa6cde4598164ed00e",
    "homepage": "https://github.com/pillarjs/cookies#readme",
    "license": "MIT",
    "maintainers": [
        {
            "name": "dougwilson"
        },
        {
            "name": "fishrock123"
        },
        {
            "name": "jed"
        },
        {
            "name": "jongleberry"
        }
    ],
    "name": "cookies",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git+https://github.com/pillarjs/cookies.git"
    },
    "scripts": {
        "test": "mocha --require test/support/env --reporter spec --bail --check-leaks test/",
        "test-ci": "istanbul cover node_modules/mocha/bin/_mocha --report lcovonly -- --require test/support/env --reporter spec --check-leaks test/",
        "test-cov": "istanbul cover node_modules/mocha/bin/_mocha -- --require test/support/env --reporter dot --check-leaks test/"
    },
    "version": "0.7.0",
    "bin": {}
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
