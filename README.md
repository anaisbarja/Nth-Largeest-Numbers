# Nth Largest Numbers

## Prompt

Write a function that can find a variable number of the largest numbers in an array without sorting.

### Input

Your function should receieve an array of numbers and the number of largest numbers.

### Output

Your function should return an array containing the requested number of values.

### Extra

What edge cases should be added?

### Hint

You may use . . .

`nameOfTheArray.splice(indexOfValueToDelete, 1) `

to delete a value in an array.

---

## Solution

### Example

nthLargestNums([1,5,7,3,4],2) //should return "[7,5]"

nthLargestNums([1,5,7,3,4],3) //should return "[7,5,4]"

    function nthLargestNums(givenArr, numLarge){
      let largestList= []
      for(i=0; i<numLarge; i++){
        let biggest=givenArr[0]
        let biggestIndex=0;
        for(j=0; j<givenArr.length; j++){
          if(biggest< givenArr[j]){
            biggest=givenArr[j]
            biggestIndex=j
          }
        }
        largestList.push(biggest)
        givenArr.splice(biggestIndex, 1)

      }
      return largestList
    }
