# How to leverage the MagicNumber pattern #IRL ?

## Magic what?

When you start reading about and trying Test-Driven Development (TDD), you very often discover the coding katas practice. And not long after you watch a video or you attend a conference and you see that the next move to answer the first failing test is to return the hardcoded value that greens the test. With the prime factors kata, it would look similar to the following.

```javascript
...
expect(primeFactorsOf(1492)).to.equal([2, 2, 373])
...
let primeFactorsOf = (number) => [2, 2, 373]
```

**[2, 2, 373]**, hardcoded value, the **MagicNumber** [[1]]. Note that some call that a **Duplication** instead. 

Then what?

And how is that useful for real life?



[1]:https://wiki.c2.com/?MagicNumber
