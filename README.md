# sm-jest-config
the sub-module of jest configuration for unit tests.

## The Sub-module path
Add this repo as the sub-module of your repo with the module path is **configs\jest**

## Recommend srciptd & npm packages
```json
{
  "scripts": {
    "git:jest": "git submodule update --init --remote configs/jest",
    "test": "jest --watch --coverage --config=configs/jest/jest.json",
    "test:ci": "npm run git:jest && jest --ci --coverage --config=configs/jest/jest.json && codecov -t <YOUR CODECOV ID>",
  },
  "devDependencies": {
    "enzyme": "latest",
    "enzyme-adapter-react-16": "latest",
    "enzyme-to-json": "latest",
    "jest": "latest",
  },
}
```
