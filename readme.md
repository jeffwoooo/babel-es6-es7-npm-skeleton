![Babel ES7 npm](https://github.frapsoft.com/top/babel-es7.jpg)

# Babel ES6 / ES7 npm Skeleton [![Javascript](https://badges.frapsoft.com/javascript/code/javascript.svg?v=100)](https://github.com/ellerbrock/javascript-badges/) [![JavaScript Style Guide](https://img.shields.io/badge/code%20style-standard-brightgreen.svg)](https://github.com/ellerbrock/javascript-badges/) [![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.svg?v=102)](https://github.com/ellerbrock/open-source-badges/) [![Gitter Chat](https://badges.gitter.im/frapsoft/frapsoft.svg)](https://gitter.im/frapsoft/frapsoft/)  

*Babel ES6 / ES7 npm Skeleton for the brave coders lifing on the edge*

## Whats inside?

- Node optimized ES6 / ES7 transpilation with [Babel](https://github.com/babel/babel)
- ES6+ aware minifier based on the Babel toolchain [babili](https://github.com/babel/babili)
- generate Sourcemaps
- Code monitoring and auto server restart with [nodemon](https://github.com/remy/nodemon)
- Code Linting with [ESLint](https://github.com/eslint/eslint)
- Javascript [Standard](https://github.com/feross/standard) Coding Style ready 
- Debugging with [babel-node-debug](https://github.com/crabdude/babel-node-debug)
- optimized npm scripts

## Ready, steady, go ...

- `git init` - create a new git repository
- `npm init -y` - create a initial package.json
- `npm install --save-dev babel-cli nodemon eslint` - install development dependencies
- `eslint --init` - setup your ESLint Style (in my case JS Standard)


## ES6

Node.js comes already with a huge set of ES6 features.
A detailed list of supported features can be found at <http://node.green>.
To speed things up and avoid transpiling stuff which is already natively supported via Node i recommend only installing the missing features for your current Node Version:

- `npm install --save-dev babel-preset-es2015-node6` - Node.js Version 6x
- `npm install --save-dev babel-preset-es2015-node5` - Node.js Version 5x
- `npm install --save-dev babel-preset-es2015-node4` - Node.js Version 4x
- `npm install --save-dev babel-preset-es2015` - for all Node.js Versions


## ES7

`npm install --save-dev babel-preset-stage-0` - for ES7 Support

## ES6+ aware Minifier

*Lets minify our production stuff directly with Babel.*

Repository: <https://github.com/babel/babili>

`npm install --save-dev babili babel-preset-babili`

## gimme some more

For more packages have a look at the <https://github.com/babel/babel/tree/master/packages> or read more about this topic on <https://babeljs.io/docs/plugins/#presets>

## package.json

To avoid messing around with separate config files like .babelrc, .eslintrc.json and so on we can put all that stuff directly in our package.json file:


```
{
  "name": "your-awesome-module",
  "version": "0.0.1",
  "babel": {
    "presets": [
      "es2015-node6",
      "stage-0",
      "babili"
    ]
  },
  "eslintConfig": {
    "extends": "standard",
    "plugins": [
      "standard",
      "promise"
    ]
  },
  "scripts": {
    "start": "nodemon $2 --exec babel-node",
    "debug": "nodemon $2 --exec babel-node --debug",
    "lint": "eslint src",
    "lint:fix": "eslint --fix src",
    "compile": "babel src -d dist",
    "compile:sourcemaps": "babel -s true src -d dist"
  },
```

## Lets run it!

- `npm start ./src/index` - Run your Code via `nodemon` transpiled with `babel-node`
- `npm run debug ./src/index` - Run and debug your Code
- `npm run lint` - lint your Code with `eslint`
- `npm run lint:fix` - lint and fix your Code with `eslint`
- `npm run compile` - Transpile your ES6 Code with `babel`
- `npm run compile:sourcemaps` - Transpile your ES6 Code with `babel` and create sourcemaps

## Debugging

At the moment of writing Node.js Version 6x is sadly not working with `node-inspector` in current Version 0.12.8. Its a known issue reported [here](https://github.com/node-inspector/node-inspector/issues/905#issuecomment-246203881).
Hopefully when you read this this problem is solved and you can install `babel-node-debug` for debugging ...

`npm install --save-dev babel-node-debug`

In this case you can change the line in your package.json

from:

`"debug": "nodemon $2 --exec babel-node --debug",`

to:

`"debug": "babel-node-debug $2",`

and run it via `npm run debug ./src/index.js`


### Contact / Social Media

*Get the latest News about Web Development, Open Source, Tooling, Server & Security*

[![Twitter](https://github.frapsoft.com/social/twitter.png)](https://twitter.com/frapsoft/)[![Facebook](https://github.frapsoft.com/social/facebook.png)](https://www.facebook.com/frapsoft/)[![Google+](https://github.frapsoft.com/social/google-plus.png)](https://plus.google.com/116540931335841862774)[![Gitter](https://github.frapsoft.com/social/gitter.png)](https://gitter.im/frapsoft/frapsoft/)[![Github](https://github.frapsoft.com/social/github.png)](https://github.com/ellerbrock/)

### Development by

Developer / Author: [Maik Ellerbrock](https://github.com/ellerbrock/)  
Company: [Frapsoft](https://github.com/frapsoft/)

### License 

Copyright (c) 2016 [Maik Ellerbrock](https://github.com/ellerbrock/)  

[![MIT Licence](https://badges.frapsoft.com/os/mit/mit-125x28.png?v=102)](https://opensource.org/licenses/mit-license.php)  

