# create-micro
> Project to create a new instance of service using [micro](https://github.com/zeit/micro).


## Installation

Install using [npm](https://www.npmjs.com/):
```
$ npm install -g create-micro
```

## Usage

### Help command

`$ create-micro --help`

Response:
```
  Usage: create-micro [options] [command]

  Commands:

    help  Display help

  Options:

    -d, --dockerfile    Include Dockerfile in the project using mhart/alpine-node (disabled by default)
    -h, --help          Output usage information
    -n, --name [value]  Name of the basic micro application (defaults to "micro-service")
    -v, --version       Output the version number
```

### Create a service

`$ create-micro -n my-application`

Response:
```
Created!

Installing packages using yarn...
yarn install v0.21.3
[1/4] Resolving packages...
[2/4] Fetching packages...
[3/4] Linking dependencies...
warning "eslint-config-prettier@1.7.0" has unmet peer dependency "eslint@>=3.14.1".
warning "request-promise@4.2.0" has unmet peer dependency "request@^2.34".
warning "request-promise-core@1.1.1" has unmet peer dependency "request@^2.34".
[4/4] Building fresh packages...
Done in 12.03s.

Done!
```

To create a Dockerfile in your service, use the flag `--dockerfile`.

`$ create-micro --dockerfile -n my-service`

### Directories

```
  - src
    - index.js
  - test
    - index.js
  - .gitignore
  - package.json
  - Dockerfile (if flag --dockerfile was used)
```

### Packages

By default, is used the last version of [micro](https://github.com/zeit/micro) and [micro-dev](https://github.com/zeit/micro-dev).

### Dockerfile

The default image is the latest version of `mhart/alpine-node`, and the Dockerfile installs just the production dependencies.

### Commands

To test you service: (XO for linting and AVA for testing functionalities)

`$ npm test`

Just to lint:

`$ npm run lint`

To start the local server:

`$ npm run dev`

To start the production server:

`$ npm start`

*Don't forget to set the NODE_ENV environment variable to `production`.*


## License

MIT License

Copyright (c) 2016 Rômulo Alves

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
