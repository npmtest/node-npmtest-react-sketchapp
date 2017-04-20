# npmtest-react-sketchapp

#### basic test coverage for  [react-sketchapp (v0.10.0)](https://github.com/airbnb/react-sketchapp)  [![npm package](https://img.shields.io/npm/v/npmtest-react-sketchapp.svg?style=flat-square)](https://www.npmjs.org/package/npmtest-react-sketchapp) [![travis-ci.org build-status](https://api.travis-ci.org/npmtest/node-npmtest-react-sketchapp.svg)](https://travis-ci.org/npmtest/node-npmtest-react-sketchapp)

#### A React renderer for Sketch.app

[![NPM](https://nodei.co/npm/react-sketchapp.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/react-sketchapp)

| git-branch : | [alpha](https://github.com/npmtest/node-npmtest-react-sketchapp/tree/alpha)|
|--:|:--|
| coverage : | [![istanbul-coverage](https://npmtest.github.io/node-npmtest-react-sketchapp/build/coverage.badge.svg)](https://npmtest.github.io/node-npmtest-react-sketchapp/build/coverage.html/index.html)|
| test-report : | [![test-report](https://npmtest.github.io/node-npmtest-react-sketchapp/build/test-report.badge.svg)](https://npmtest.github.io/node-npmtest-react-sketchapp/build/test-report.html)|
| build-artifacts : | [![build-artifacts](https://npmtest.github.io/node-npmtest-react-sketchapp/glyphicons_144_folder_open.png)](https://github.com/npmtest/node-npmtest-react-sketchapp/tree/gh-pages/build)|

- [https://npmtest.github.io/node-npmtest-react-sketchapp/build/coverage.html/index.html](https://npmtest.github.io/node-npmtest-react-sketchapp/build/coverage.html/index.html)

[![istanbul-coverage](https://npmtest.github.io/node-npmtest-react-sketchapp/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fcoverage.lib.html.png)](https://npmtest.github.io/node-npmtest-react-sketchapp/build/coverage.html/index.html)

- [https://npmtest.github.io/node-npmtest-react-sketchapp/build/test-report.html](https://npmtest.github.io/node-npmtest-react-sketchapp/build/test-report.html)

[![test-report](https://npmtest.github.io/node-npmtest-react-sketchapp/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Ftest-report.html.png)](https://npmtest.github.io/node-npmtest-react-sketchapp/build/test-report.html)

- [https://npmdoc.github.io/node-npmdoc-react-sketchapp/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-react-sketchapp/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-react-sketchapp/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-react-sketchapp/build/apidoc.html)

![npmPackageListing](https://npmtest.github.io/node-npmtest-react-sketchapp/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmtest.github.io/node-npmtest-react-sketchapp/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "name": "react-sketchapp",
    "version": "0.10.0",
    "description": "A React renderer for Sketch.app",
    "main": "lib/index.js",
    "license": "MIT",
    "author": "Jon Gold <jon.gold@airbnb.com> (http://jon.gold)",
    "contributors": [
        "Ben Wilkins <ben.wilkins@airbnb.com>",
        "Leland Richardson <leland.richardson@airbnb.com>"
    ],
    "pre-commit": "lint-staged",
    "scripts": {
        "build:react": "babel src -d lib --ignore **/__mocks__/**",
        "build:flow": "flow-copy-source -v -i '**/__tests__/**' src lib",
        "build": "npm run build:react && npm run build:flow",
        "clean": "rimraf lib react-example.sketchplugin",
        "check": "npm run test && npm run flow && npm run lint",
        "docs:clean": "rimraf _book",
        "docs:prepare": "gitbook install",
        "docs:build": "npm run docs:prepare && gitbook build",
        "docs:watch": "npm run docs:prepare && gitbook serve",
        "docs:publish": "npm run docs:clean && npm run docs:build && cd _book && git init && git commit --allow-empty -m 'update book' && git fetch git@github.com:airbnb/react-sketchapp.git gh-pages && git checkout -b gh-pages && git add . && git commit -am 'update book' && git push git@github.com:airbnb/react-sketchapp.git gh-pages --force",
        "flow": "flow",
        "lint": "eslint .",
        "lint-staged": "lint-staged",
        "prepublishOnly": "npm run clean && npm run check && npm run build",
        "test": "jest --config .jestrc",
        "test:ci": "jest --config .jestrc --runInBand",
        "test:watch": "npm run test -- --watch",
        "watch": "npm run build:react -- --watch"
    },
    "dependencies": {
        "css-layout": "^1.1.1",
        "error-stack-parser": "^2.0.0",
        "invariant": "^2.2.2",
        "murmur2js": "^1.0.0",
        "normalize-css-color": "^1.0.1",
        "sketch-constants": "^1.0.2",
        "sketchapp-json-flow-types": "^0.0.3",
        "sketchapp-json-plugin": "^0.0.3"
    },
    "peerDependencies": {
        "react": "*",
        "react-test-renderer": "*"
    },
    "keywords": [
        "sketch",
        "sketchapp",
        "react",
        "reactjs",
        "renderer"
    ],
    "repository": {
        "type": "git",
        "url": "https://github.com/airbnb/react-sketchapp"
    },
    "bugs": {
        "url": "https://github.com/airbnb/react-sketchapp/issues"
    },
    "homepage": "https://github.com/airbnb/react-sketchapp",
    "lint-staged": {
        "*.js": [
            "prettier-eslint --write \"src/**/*.js\"",
            "git add"
        ]
    },
    "devDependencies": {
        "@jongold/eslint-config-sketch": "^1.0.0-2",
        "babel-cli": "^6.18.0",
        "babel-core": "^6.0.0",
        "babel-eslint": "^7.1.0",
        "babel-jest": "^18.0.0",
        "babel-plugin-transform-flow-strip-types": "^6.18.0",
        "babel-polyfill": "^6.20.0",
        "babel-preset-es2015": "^6.18.0",
        "babel-preset-react": "^6.16.0",
        "babel-preset-stage-0": "^6.16.0",
        "eslint": "^3.9.1",
        "eslint-config-airbnb": "^12.0.0",
        "eslint-plugin-import": "^1.16.0",
        "eslint-plugin-jsx-a11y": "^2.2.3",
        "eslint-plugin-react": "^6.4.1",
        "flow-bin": "^0.36.0",
        "flow-copy-source": "^1.1.0",
        "gitbook-cli": "^2.3.0",
        "jest-cli": "^18.1.0",
        "lint-staged": "^3.4.0",
        "pre-commit": "^1.2.2",
        "prettier-eslint-cli": "^3.1.2",
        "react": "^15.4.1",
        "react-test-renderer": "^15.4.1",
        "rimraf": "^2.5.4"
    }
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
