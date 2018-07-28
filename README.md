# sm-jest-config

the sub-module of jest configuration for unit tests.

## The Sub-module path

Add this repo as the sub-module of your repo with the module path is **configs\jest**

## Recommend srciptd & npm packages

### TypeScript Project

1.  Apply the Dev Dependencies as below

```json
{
  "scripts": {
    "git:jest": "git submodule update --init --remote configs/jest",
    "test":
      "npm run git:jest && jest --watch --coverage --config=configs/jest/jest.json",
    "test:ci":
      "npm run git:jest && jest --ci --coverage --config=configs/jest/jest.json && codecov -t <YOUR CODECOV ID>"
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
  "presets": [],
  "plugins": [],
  "env": {
    "test": {
      "presets": ["env"],
      "plugins": ["transform-es2015-modules-commonjs"]
    }
  }
}
```

### Javascript Project
