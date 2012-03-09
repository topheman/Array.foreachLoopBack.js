Array.foreachLoopBack.js

Array.foreachLoopBack.js extends the native javascript Array object to add the foreachLoopBack method to the prototype that allows you to loop from any index to any other in your array, looping back at the end of it without bothering about indexes.

You can see the examples live on http://labs.topheman.com/Array.foreachLoopBack

You can see it in action on http://squares.topheman.com

There the post about Array.foreachLoopBack on my blog

Examples

```js
var test = [
    'a','b','c','d','e','f','g','h','i','j'
];
//conventional use (as if it was a for or for as loop)
test.foreachLoopBack(function(elem){console.info(elem)});//outputs : abcdefghij
//same but reverse
test.foreachLoopBack(function(elem){console.info(elem)}, true);//outputs : jihgfedcba
//from index 3 - this will loopback at the end of the array if no indexStop specified
test.foreachLoopBack(function(elem){console.info(elem)}, false,3);//outputs : defghijabc
//same but reverse
test.foreachLoopBack(function(elem){console.info(elem)}, true,3);//outputs : cbajihgfed
//from index 3 to index 8
test.foreachLoopBack(function(elem){console.info(elem)}, false,3,8);//outputs : defghi
//from index 3 to index 8 - reversed
test.foreachLoopBack(function(elem){console.info(elem)}, true,3,8);//outputs : ihgfed
//from index 8 to index 3 - will loopback at the end of the array
test.foreachLoopBack(function(elem){console.info(elem)}, false,8,3);//outputs : ijabcd
//from index 8 to index 3 - reversed
test.foreachLoopBack(function(elem){console.info(elem)}, true,8,3);//outputs : dcbaji
```

Todo

* Injecting this method directly to the prototype of the native type Array may appear intrusive to some of you (I'd agree) - so if you want to implement it in an other way (like a jQuery plugin ...) feel free to (let me know).