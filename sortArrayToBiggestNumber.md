## Problem: create a function that sort the array of numbers to form the largest number.
e.g. Root array: [20, 3 ,5, 45] => Sorted array [5, 45, 3, 20] => 545320 (biggest number)

```js
const arr = [10, 20, 3 ,5, 45, 7, 13];
function biggestNum(arr){
  arr.reverse();
  let arrLen = arr.length;

  for(let i = 0; i < arrLen - 1; i++){
      let max = parseInt(arr[i].toString()[0]);
      let index;
      for(let j = i+1; j < arrLen; j++){
          let second = parseInt(arr[j].toString()[0]);
          if(max < second){
              max = second;
              index = j;
          }
      }
      if(index){
          let temp = arr[i];
          arr[i] = arr[index];
          arr[index] = temp;
      }
  }
  return arr;
}
console.log(biggestNum(arr));
```
