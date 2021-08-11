# How to leverage the MagicNumber pattern #IRL ?

## Magic what?

When you start reading about and trying Test-Driven Development (TDD), you very often discover the coding katas practice. And not long after you watch a video or you attend a conference and you see that the next move to answer the first failing test is to return the hardcoded value that greens the test. With the prime factors kata, it would look similar to the following.

```javascript
expect(primeFactorsOf(1492)).to.equal([2, 2, 373])

let primeFactorsOf = (number) => [2, 2, 373]
```

**[2, 2, 373]**, hardcoded value, the **MagicNumber** [[1]]. Note that some call that a **Duplication** instead.

Then what?

And how is that useful for real life?

## Next move

Assuming a coding kata is useful for real life, then I want the next move to build up my muscle memory for real life. When all my tests are green I have 2 options: a: write a new test, or b: refactor. Maybe in real life, I have no idea which new test to write, or maybe I have no clue how to refactor the current code.  Maybe the  test is an internal test exercising an internal class, or maybe the test is an external test like a Selenium test clicking on a page and expecting something that the current code produces with a MagicNumber.

What works well for me at that stage is to **move the MagicNumber** inside my architecture, creating it if needed. In the context of a coding kata, it could mean something like the following.

```javascript
expect(primeFactorsOf(1492)).to.equal([2, 2, 373])

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

We moved the MagicNumber. Test is still green. And the production code is one step further towards my target.

What is the next move now? Now I have the opportunity to write an internal test against the Mathematician class, instead of writing another external test. This is also something I want to practice. I don't want to rely only on external tests. Remember the test pyramid [[2]]!

## In Real Life

In the context of a web app, when the http request hits the server, then probably the http component will ask for help to another component. Moving the MagicNumber in this other component makes you remove it from the http component. In order to do that, chances are your http component will have to be more generic, cleaner, and the refactoring opportunities will move along with the MagicNumber to the other component.

Thanks to the coding kata practice, my muscles memory is telling me to write internal tests along with this refactoring effort of moving and eventually removing the MagicNumber.

I continue the game of moving the MagicNumber in the architecture until I hit a leaf: no more other component to which I can push the MagicNumber. This is when time has come to remove the MagicNumber. 

You probably noted that I am a big fan of the outside-in tdd approach which works very well for me with the hexagonal architecture [[3]]. When the first test is an external test, like a Selinium test for example, you could be in a position where the leaf that you hit is an adapter and you have to fetch data from a store to remove the MagicNumber. Chances are that when you do that the test will turn red because you did not insert anything in the first place because it was not the fastest way to green the test. When that happens, don't panic, just use MagicNumber again on the writing-data side of the story. This is when having written internal tests during the first phase is a fantastic level that makes this second phase very fast.

Hope that helps :)


[1]:https://wiki.c2.com/?MagicNumber
[2]:https://martinfowler.com/articles/practical-test-pyramid.html
[3]:https://alistair.cockburn.us/hexagonal-architecture/

