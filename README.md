# bitArray.js
A simple, well commented, pure Javascript implementation of a bit array for storing and manipulating boolean values. 

### Why should I use this?

This library is being developed in order to provide javascipt developers with an intuitue, simple API to store a large
number of boolean (true/false) values with minimal overhead.  Accessing values and changing them are all constant in their
time complexity (excluding the 'trueBits' and 'percentTrue' methods).  Under the hood, this library uses bitwise operations on
unsigned 8 bit integers, so it's memory and processor consumtion is at an absolute minimum.  

### What are some usage cases?

Originally this library was developed to assist with a learning repo, 
[LearnBloomFilters](https://github.com/TheAdamizer/LearnBloomFilter), which is a testing driven repo to help javascript 
developers create a bloom filter implementation.  To implement a bloom filter well, the developer requries a high performance
way to manipulate a large array of boolean values, so this library was an answer to that requirement.  Although it excels in
this function, it is suitable to act as a boolean array where vanilla javascript is the required platform.

### How do I use it?

First, the developer needs to instantiate a new BitArray object using the [new](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new)
operator and calling the BitArray constructor, passing in the desired length of the array as the only parameter.

```javascript
var ba = new BitArray(100);
```

Now you have a bit array!  By default, every bit in the array is set to 0 (false).  To turn on a bit in the array, simply call
the flipOn method and pass in the desired index you would like to set to 1 (true).

```javascript
ba.flipOn(50);
```

If you would like to determine the value of a bit at a given index, simply call the check method on the BitArray object and
pass in the index you are curious about.

```javascript
ba.check(50);
\\ returns true;
ba.check(75);
\\ returns false;
```

The BitArray object also has a method for determining the amount of bits that are true in the array relative to the total 
length of the array.  This method is called percentTrue.

```javascript
ba.percentTrue();
\\ returns .01
```
