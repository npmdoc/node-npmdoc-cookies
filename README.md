# npmdoc-cookies

#### api documentation for  cookies (v0.7.0)  [![npm package](https://img.shields.io/npm/v/npmdoc-cookies.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-cookies) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-cookies.svg)](https://travis-ci.org/npmdoc/node-npmdoc-cookies)

#### Cookies, optionally signed using Keygrip.

[![NPM](https://nodei.co/npm/cookies.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/cookies)

- [https://npmdoc.github.io/node-npmdoc-cookies/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-cookies/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-cookies/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-cookies/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-cookies/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-cookies/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "name": "cookies",
    "description": "Cookies, optionally signed using Keygrip.",
    "version": "0.7.0",
    "author": "Jed Schmidt <tr@nslator.jp> (http://jed.is)",
    "contributors": [
        "Douglas Christopher Wilson <doug@somethingdoug.com>"
    ],
    "license": "MIT",
    "repository": "pillarjs/cookies",
    "dependencies": {
        "depd": "~1.1.0",
        "keygrip": "~1.0.1"
    },
    "devDependencies": {
        "express": "4.9.8",
        "istanbul": "0.4.5",
        "mocha": "2.5.3",
        "restify": "2.8.1",
        "supertest": "1.1.0"
    },
    "files": [
        "HISTORY.md",
        "LICENSE",
        "README.md",
        "index.js"
    ],
    "engines": {
        "node": ">= 0.8"
    },
    "scripts": {
        "test": "mocha --require test/support/env --reporter spec --bail --check-leaks test/",
        "test-ci": "istanbul cover node_modules/mocha/bin/_mocha --report lcovonly -- --require test/support/env --reporter spec --check-leaks test/",
        "test-cov": "istanbul cover node_modules/mocha/bin/_mocha -- --require test/support/env --reporter dot --check-leaks test/"
    }
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
