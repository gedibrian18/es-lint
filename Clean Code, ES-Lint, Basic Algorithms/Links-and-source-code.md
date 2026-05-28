# JS-Advanced - Clean Code, ES-Lint, Basic Algorithms

## Video link:

https://youtu.be/wnTivNtDcsQ

## CLEAN CODER KÖNVY

https://drive.google.com/file/d/11JouLMVekBVB9M15kvM5tq5DMzhWvaZP/view
https://drive.google.com/drive/folders/1Au9rwtI4xBy-qzBxjsNTMzZeGmMf1_8H?usp=sharing

```javascript
// formázott
let isTrue = true;

if (isTrue) {
  console.log('True');
} else {
  if (isTrue) {
    console.log('inside true');
  }
  console.log('False');
}
// nem formázott
// let isTrue2 = true;if (isTrue2) {console.log('True');} else {if (isTrue2) {console.log('inside true');}console.log('False');}

// variables

let myVariable = 'valami';
let isActive = true;
const BASE_URL = 'https';

// fucntions

calculateTotalPrice();

// comments

// 1 line
/* multiple line
multiple line
multiple line */

// három egyenlőségjel használata
0 === '0';

// string "John" vagy 'John'

// 1 sor max 120-140 karakter
```

## ES-Lint

Extension telepítése: ESLint

https://www.npmjs.com/

https://eslint.org/

```bash
npm init @eslint/config
```

https://eslint.org/docs/latest/use/getting-started

https://www.npmjs.com/package/eslint-config-airbnb

https://eslint.org/docs/latest/rules/no-console#rule-details

```javascript
{
  rules: {
    'no-console': 'error',
  },
}
```

```javascript
{
rules: {
    'no-console': ['error', { allow: ['warn', 'error'] }],
  },
},
```

## Clean Code practices

```javascript
const correctResults = [
  'Result of addition: 35',
  'Result of subtraction: 9',
  'Result of multiplication: 24',
  'Result of divison: 4',
];

const testCases = [
  [12, 23, 'add', 'calculate'],
  [12, 3, 'sub', 'calculate'],
  [12, 2, 'multiply', 'calculate'],
  [12, 3, 'divide', 'calculate'],
];

console.log(calculatorController(12, 3, 'add', 'calculate'));
console.log(calculatorController(12, 3, 'sub', 'calculate'));
console.log(calculatorController(12, 3, 'divide', 'calculate'));
console.log(calculatorController(12, 3, 'multiply', 'calculate'));
console.log(calculatorController(12, 3, 'add', 'test'));

function calculatorController(num1, num2, operation, command) {
  if (!chechParameters(num1, num2, operation)) return 'invalid operation';
  if (command === 'calculate') return runCalculator(num1, num2, operation);
  if (command === 'test') return testingCalculator();
}

function chechParameters(num1, num2, operation) {
  return (
    typeof num1 === 'number' &&
    typeof num2 === 'number' &&
    typeof operation === 'string'
  );
}

function runCalculator(num1, num2, operation) {
  switch (operation) {
    case 'add':
      return `Result of addition: ${num1 + num2}`;
    case 'sub':
      return `Result of subtraction: ${num1 - num2}`;
    case 'multiply':
      return `Result of multiplication: ${num1 * num2}`;
    case 'divide':
      return `Result of divison: ${num1 / num2}`;
    default:
      return 'invalid operation! Options: add, sub, divide, multiply!';
  }
}

function testingCalculator() {
  let isFailed = false;
  testCases.forEach((element, index) => {
    if (runCalculator(...element) !== correctResults[index]) isFailed = true;
  });
  return isFailed ? 'Tests failed' : 'All tests passed...';
}
```

## Basic Algorithms

https://www.youtube.com/watch?v=nmhjrI-aW5o

https://www.youtube.com/watch?v=BeoCbJPuvSE
