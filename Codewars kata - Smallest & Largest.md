# Codewars kata: 'Smallest and largest digits in smallest integer'
https://www.codewars.com/kata/5c6b004eea8d3246d02160de/edit/javascript

## THE CHALLENGE:
Take a random *positive* integer with 0<n<17 digits, each of which is also positive, and rearrange the digits to return a string containing:
1.  the smallest possible integer, comprising all digits
2.  a single instance of the smallest digit (i.e., if there are several instances of the smallest digit, output it just once)
3.  the index position of the smallest digit in the *original* integer.
4.  a single instance of the largest digit.

For example: if you input the number `96781191` in the `smallestNum` function, you should get `'11167899, 1, 4, 9'`.

## COMPLETE SOLUTION
```
const smallestNum = num => {

let nDigits = num.toString().split('');
// console.log(nDigits);

let realNum = nDigits.map(function(x) {
  return parseInt(x, 10);
});
// console.log(realNum);

let minNum = Math.min(...realNum);
// console.log(minNum);

let indMin = realNum.indexOf(minNum);
// console.log(indMin);

let maxNum = Math.max(...realNum);
// console.log(maxNum);

let numStr = realNum.sort(function(a, b) {
  return a - b;
});
// console.log(numStr);

let newNum = numStr.join('');
// console.log(newNum);


let result = newNum.concat(', ', minNum).concat(', ', indMin).concat(', ', maxNum);

return result;
}

smallestNum(53772369);
```
## TEST CASES
```
// Need to add tests for random numbers

const chai = require("chai");
const assert = chai.assert;
chai.config.truncateThreshold = 0;


describe('smallestNum', function() {

  it('given (6)', function() {
    assert.deepEqual(smallestNum(6), '6, 6, 0, 6')
  });
  
  it('given (123)', function() {
    assert.deepEqual(smallestNum(123), '123, 1, 0, 3')
  });
  
   it('given (1895891)', function() {
    assert.deepEqual(smallestNum(1895891), '1158899, 1, 0, 9')
  });
  
  it('given (444444444444)', function() {
    assert.deepEqual(smallestNum(444444444444), '444444444444, 4, 0, 4')
  });
  
   it('given (3333353)', function() {
    assert.deepEqual(smallestNum(3333353), '3333335, 3, 0, 5')
  });
  
  it('given (568992)', function() {
    assert.deepEqual(smallestNum(568992), '256899, 2, 5, 9')
  });
  
  it('given (9345619723612765)', function() {
    assert.deepEqual(smallestNum(9345619723612765), '1122334456667799, 1, 5, 9')
  });
  
  it('given (4788946221459834)', function() {
    assert.deepEqual(smallestNum(4788946221459834), '1223444456788899, 1, 9, 9')
  });
  
   it('given (1)', function() {
    assert.deepEqual(smallestNum(1), '1, 1, 0, 1')
  });
  
  it('given (19)', function() {
    assert.deepEqual(smallestNum(19), '19, 1, 0, 9')
  });

   it('given (91)', function() {
    assert.deepEqual(smallestNum(91),  '19, 1, 1, 9')
  });

  it('given (515151)', function() {
    assert.deepEqual(smallestNum(515151), '111555, 1, 1, 5')
  });
  
  it('given (55555555)', function() {
    assert.deepEqual(smallestNum(55555555), '55555555, 5, 0, 5')
  });

  it('given(77769219888)', function() {
    assert.deepEqual(smallestNum(77769219888), '12677788899, 1, 6, 9')
  });

  it('given(5237891432995127)', function() {
    assert.deepEqual(smallestNum(5237891432995127), '1122233455778999, 1, 6, 9')
  });

});
```

## EXAMPLE TESTS
```
const chai = require("chai");
const assert = chai.assert;
chai.config.truncateThreshold = 0;


describe('smallestNum', function() {
 
 it('given (6)', function() {
    assert.deepEqual(smallestNum(6), '6, 6, 0, 6')
  });
  
  it('given (123)', function() {
    assert.deepEqual(smallestNum(123), '123, 1, 0, 3')
  });
  
   it('given (1895891)', function() {
    assert.deepEqual(smallestNum(1895891), '1158899, 1, 0, 9')
  });
  
  it('given (444444444444)', function() {
    assert.deepEqual(smallestNum(444444444444), '444444444444, 4, 0, 4')
  });
  
   it('given (3333353)', function() {
    assert.deepEqual(smallestNum(3333353), '3333335, 3, 0, 5')
  });
  
});
```
