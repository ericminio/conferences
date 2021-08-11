# How to leverage the MagicNumber pattern #IRL ?

## Magic what?

When you start reading about and trying Test-Driven Development (TDD), you very often discover the coding kata practice. And you see that the next move to answer the first failing test is to return a hardcoded value that greens the test. With the prime factors kata, it would look similar to the following.

```javascript
expect(primeFactorsOf(1492)).to.deep.equal([2, 2, 373])

let primeFactorsOf = (number) => [2, 2, 373]
```

**[2, 2, 373]**, hardcoded value, the **MagicNumber**[[1]]. Note that some call that a Duplication instead.

Then what?

And how is that useful for real life?

## Next move

Assuming a coding kata is useful for real life, then I want the practice to build up my muscle memory for real life. When all my tests are green I have 2 options: a: write a new test, or b: refactor. Maybe in real life, I have no idea which new test to write, or maybe I have no clue how to refactor the current code.  Maybe the  test is an internal test exercising an internal class, or maybe the test is an external test like a Selenium test clicking on a page and expecting something that the current code produces with a MagicNumber.

What works well for me is to **move the MagicNumber** inside my architecture, creating it if needed. In the context of a coding kata, it could mean something like the following.

```javascript
expect(primeFactorsOf(1492)).to.deep.equal([2, 2, 373])

let primeFactorsOf = (number) => {
    let max = new Mathematician();
    return max.primesOf(number);
}

class Mathematician {
  
    primesOf(number) {
        return [2, 2, 373];
    }
}
```

We moved the MagicNumber. Test is still green. And our architecture emerges if not already existing.

What is the next move now? Now I have the opportunity to triangulate with an internal test against the Mathematician class, instead of writing another external test. This is also something I want to practice. I don't want to rely only on external tests. Remember the test pyramid[[2]]!

## In Real Life

In the context of a web app, when the http request hits the server, then the http component will ask for help to another component. Moving the MagicNumber in this other component makes you remove it from the http component which becomes more generic. The refactoring opportunities will move to the next component and I can repeat the pattern from there.

Thanks to the coding kata practice, my muscles memory is telling me to write internal tests during this refactoring effort of moving and eventually removing the MagicNumber. 

There is a special moment in this journey when I hit what looks like a leaf in the architecture, usually an adapter[[3]]. If I simply remove the MagicNumber then chances are that the external test will turn red because I did not insert any data in the first place. To stay green, I actually have to continue with moving the MagicNumber, this time on the writing-data side of the story.

Hope that helps :)


[1]:https://wiki.c2.com/?MagicNumber
[2]:https://martinfowler.com/articles/practical-test-pyramid.html
[3]:https://alistair.cockburn.us/hexagonal-architecture
