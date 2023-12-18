# CHALLENGE :: TESTS & CODE REFINEMENT

## TESTS :: mocks & spies

### 🧪 `transformStringToCollection` test refinement

- mock `onError` & `onSuccess` callbacks using `jest.fn`
const onErrorMock = jest.fn();
const onSuccessMock = jest.fn();
- check callbacks have been called only once
transformStringToCollection("test", onErrorMock, onSuccessMock);
expect(onErrorMock).toHaveBeenCalledTimes(1);
expect(onSuccessMock).toHaveBeenCalledTimes(1);

- check result is the expected one for all cases defined at `index.js`

### 🧪 `createUser` test refinement

- mock `onError` & `onSuccess` callbacks using `jest.fn`
const onErrorMock = jest.fn();
const onSuccessMock = jest.fn();
createUser("ADRI", onErrorMock, onSuccessMock);
expect(onErrorMock).toHaveBeenCalledTimes(1);
expect(onSuccessMock).toHaveBeenCalledTimes(1);

- spy `Math.random` to control returned value

- check callbacks have been called only once
const mockRandom = jest.spyOn(Math, 'random').mockReturnValue(0.7);
createUser("ADRI", onErrorMock, onSuccessMock);

- check result is the expected one for all cases defined at `index.js`

## CODE REFINEMENT :: defining helpers

1 - Create folder `helpers` at project root leve

2 - Create and export file `validateString` file as helper

3 - Define logic to validate string

- signature:
  - input: value
  - output: boolean
- validation logic:
  - if value is undefined 👉 `false`
  - if typeof value is different to 'string' 👉 `false`
  - if value is an empty string 👉 `false`

4 - Define `validateString.test.js` test cases

- when value is undefined
- when value is number
- when value is array
- when value is boolean
- when value is an object
- when value is an empty string
- when value is fulfilled string

5 - Implement validator in `transformStringToCollection` & `createUser`