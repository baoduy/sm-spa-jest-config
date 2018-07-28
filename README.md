# sm-jest-config

the sub-module of jest configuration for unit tests.

## The Sub-module path

Add this repo as the sub-module of your repo with the module path is **configs\jest**

## Recommend srciptd & npm packages

### TypeScript Project

1.  Apply the Dev Dependencies as below
    Remove the `&& codecov -t <YOUR CODECOV ID>` in the `test:ci` if you are not using CODECOV.

```json
{
  "scripts": {
    "git:jest": "git submodule update --init --remote configs/jest",
    "test":
      "npm run git:jest && jest --watch --coverage --config=configs/jest/ts.jest.json",
    "test:ci":
      "npm run git:jest && jest --ci --coverage --config=configs/jest/ts.jest.json && codecov -t <YOUR CODECOV ID>"
  },
  "devDependencies": {
    "babel-cli": "^6.26.0",
    "babel-jest": "^23.4.2",
    "babel-plugin-transform-es2015-modules-commonjs": "^6.26.2",
    "env": "0.0.2",
    "enzyme": "3.3.0",
    "enzyme-adapter-react-16": "1.1.1",
    "enzyme-to-json": "3.3.4",
    "jest": "23.4.1",
    "jsdom": "11.12.0",
    "jsdom-global": "3.0.2",
    "ts-jest": "^23.0.1"
  }
}
```

2.  Config the **.babelrc** file as below

```json
{
  "presets": [
    //Your presets
  ],
  "plugins": [
    //Your plugins
  ],
  "env": {
    //This for jest test
    "test": {
      "presets": ["env"],
      "plugins": ["transform-es2015-modules-commonjs"]
    }
  }
}
```

### Javascript Project

1.  Apply the Dev Dependencies as below
    Remove the `&& codecov -t <YOUR CODECOV ID>` in the `test:ci` if you are not using CODECOV.

```json
{
  "scripts": {
    "git:jest": "git submodule update --init --remote configs/jest",
    "test":
      "npm-run-all git:jest && jest --watch --coverage --config=configs/jest/jest.json",
    "test:ci":
      "npm-run-all git:jest && jest --ci --coverage --config=configs/jest/jest.json && codecov -t <YOUR CODECOV ID>"
  },
  "devDependencies": {
    "babel-cli": "6.26.0",
    "babel-core": "6.26.3",
    "babel-eslint": "8.2.6",
    "babel-jest": "23.4.0",
    "babel-loader": "7.1.5",
    "babel-plugin-module-resolver": "3.1.1",
    "babel-preset-env": "1.7.0",
    "babel-preset-react-latest": "6.1.0",
    "enzyme": "^3.3.0",
    "enzyme-adapter-react-16": "^1.1.1",
    "enzyme-to-json": "^3.3.4",
    "jest": "23.4.1",
    "npm-run-all": "^4.1.3"
  }
}
```

2.  Config the **.babelrc** file as below

```json
{
  "presets": [
    //Your presets
  ],
  "plugins": [
    //Your plugins
  ],
  //This for jest test
  "env": {
    "test": {
      "presets": ["env", "react-latest"],
      "plugins": ["transform-es2015-modules-commonjs"]
    }
    //Your other environments
  }
}
```
