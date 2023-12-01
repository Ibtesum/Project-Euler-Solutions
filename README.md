# Project-Euler-Solutions
## Problem 1: Multiples of 3 and 5
If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.

Find the sum of all the multiples of 3 or 5 below the provided parameter value number.

My solution: 
```
function multiplesOf3and5(number) {
  let multiples = []
  for(let i = 1; i< number; i++){
    if(i % 3===0 && i% 5 === 0){
      multiples.push(i)
    } else if(i%5 === 0){
      multiples.push(i)
    } else if(i%3 === 0){
      multiples.push(i)
    }
  }
  return multiples.reduce((acc, curr)=> acc + curr, 0);
}

multiplesOf3and5(1000);
```

FCC solution 1: 

```
function multiplesOf3and5(number) {
  let sum = 0,
    i = 3;
  while (i < number) {
    if (i % 3 == 0 || i % 5 == 0) sum += i;
    i++;
  }
  return sum;
}
```

FCC solution 2: 

```
function multiplesOf3and5(number) {
  // sum of multiples of 3
  const numMultOf3 = Math.floor((number - 1) / 3, 10);
  const sum3 = (numMultOf3 * (numMultOf3 + 1) / 2) * 3;

  // sum of multiples of 5
  const numMultOf5 = Math.floor((number - 1) / 5, 10);
  const sum5 = (numMultOf5 * (numMultOf5 + 1) / 2) * 5;

  // sum of multiples of 15 (both 3 and 5)
  // we need to subtract these because they are added twice
  const numMultOf15 = Math.floor((number - 1) / 15, 10);
  const sum15 = (numMultOf15 * (numMultOf15 + 1) / 2) * 15;

  return sum3 + sum5 - sum15;
}
```
