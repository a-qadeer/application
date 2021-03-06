<div align="center">
  <img src="https://res.cloudinary.com/adonisjs/image/upload/q_100/v1564392111/adonis-banner_o9lunk.png" width="600px">
</div>

# Adonis application
[![circleci-image]][circleci-url] [![npm-image]][npm-url] ![][typescript-image] [![license-image]][license-url]

The application class for AdonisJs to know more about the environment and project structure of your AdonisJs applications.

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
## Table of contents

- [Usage](#usage)
- [rcParser](#rcparser)
- [API Docs](#api-docs)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Usage
Ideally you shouldn't be installing this module directly, since it is part of AdonisJs by default. However, installing module directly is helpful when testing AdonisJs specific addons.

```sh
npm i @adonisjs/application

# Yarn
yarn add @adonisjs/application
```

and then use it as follows:

```ts
import { Application } from '@adonisjs/application/build/standalone'
import { Ioc } from '@adonisjs/fold'

const app = new Application(
  __dirname,
  new Ioc(),
  require('./adonisrc.json'),
  require('./package.json'),
)
```

The constructor takes 4 arguments, which you can fake during tests.

| Argument position | Description |
|------------------|------------------|
| `1 (appRoot)` | The application root |
| `2 (ioc)` | Instance of IoC container |
| `3 (rcContents)` | Contents of `.adonisrc.json` file. You can also provide an empty object |
| `4 (pkgFile)` | Pass the contents of `package.json` file. Required to pull the app name, version and so on |

## rcParser
The application instance will parse the contents of `.adonisrc.json` file. However, if you need the parser, you can access and use it as follows.

```ts
import { rcParser } from '@adonisjs/application/build/standalone'
rcParser.parse(require('.adonisrc.json'))
```

## API Docs
Following are the autogenerated files via Typedoc

* [API](docs/README.md)

[circleci-image]: https://img.shields.io/circleci/project/github/adonisjs/application/master.svg?style=for-the-badge&logo=circleci
[circleci-url]: https://circleci.com/gh/adonisjs/application "circleci"

[typescript-image]: https://img.shields.io/badge/Typescript-294E80.svg?style=for-the-badge&logo=typescript
[typescript-url]:  "typescript"

[npm-image]: https://img.shields.io/npm/v/@adonisjs/application.svg?style=for-the-badge&logo=npm
[npm-url]: https://npmjs.org/package/@adonisjs/application "npm"

[license-image]: https://img.shields.io/npm/l/@adonisjs/application?color=blueviolet&style=for-the-badge
[license-url]: LICENSE.md "license"
