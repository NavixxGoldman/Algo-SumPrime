# Algo-SumPrime
This is an algorithm to sum all prime numbers with the "Sieve of Erathostenes"

```javascript
function sumPrimes(num) {
    var newArray=new Array(num);
    var primeArray=[];
    //Set Array with boolean values
    newArray[0]=false;
    newArray[1]=false;
   //Mark all true
  for (var i=2;i<=num;i++){
       newArray[i]=true;
  }
  //Mark all multiple as false
   for (var p=2;p<Math.sqrt(num);p++){
       if (newArray[p]){
          for(var j = p*p; j <= num; j += p)
        newArray[j] = false;
       }
  }
  // Get all the prime numbers
  for (var i = 0; i <=num; i++)
    if(newArray[i]) primeArray.push(i);

//Sum PrimeArray
var finalArray= primeArray.reduce((a,b)=>a+b,0);
  return finalArray;

}

console.log(sumPrimes(10));
console.log(sumPrimes(977));
```
