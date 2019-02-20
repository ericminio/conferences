5 slides:

- http://agilemanifesto.org/

- https://martinfowler.com/bliki/FlaccidScrum.html

- https://www.google.com/search?q=Extreme+Programming&client=firefox-b-ab&source=lnms&tbm=isch&sa=X&ved=0ahUKEwjt_PLukK3eAhXyKX0KHQ4KDEIQ_AUIDigB&biw=1262&bih=858#imgrc=poBCYsjQZUtIeM:

- https://www.google.com/search?q=TDD&client=firefox-b-ab&source=lnms&tbm=isch&sa=X&ved=0ahUKEwjPqKuGka3eAhXELH0KHcGLCfsQ_AUIEygA&biw=1262&bih=858#imgrc=bUbC7PaEYT45EM:

- https://www.scrum.org/about

# Notes

How to make Agile work?

What is the promise of Agile in the first place?

From the Agile Manifesto, we can extrapolate some promises. This manifesto has several sections that we can study one by one and all together:
1. An introduction
2. A section usually called the values
3. A general insight about the values
4. A second page listing 12 principles

It is in the second page that the promise of Agile is actually disclosed. 

Some might argue that the first page is full of promises. I simply find some elements in the second page way easier to measure, assess, or implement.

Out of the 12 principles, the 3 first are focussing on customer satisfaction, early and frequent deliveries, being very clear that by frequent we mean a pace between a couple of weeks and a couple of months.

So, from a customer point of view, the promise is crystal clear: Agile means that he/she can expect an agile team to deliver a valuable working software every couple of months. It is a fair expectation for any customer / client / Product Owner to have after reading this manifesto in front of a team / company pretending to be agile.

The target is set. 

This target is very intimidating. Think about it seriously. Monday morning you start the clock and in a couple of months later you and your team will deliver a valuable working software to your customer, and, if relevant, you will keep the pace of adding at least one valuable feature after another couple of months, and so on… And this couple-of-months is said to be the minimal pace… And take working and valuable software for what it is: software deployed in production and used by someone.

So, how does a team deliver such promise?

The agile manifesto is actually full of advices about how to make Agile work.

Some advices are crystal clear: 
* principle #4: business people and developers must work together daily throughout the project. 
* principle #6: The most efficient and effective method of conveying information to and within a development team is face-to-face conversation.
* Principle #12: At regular intervals, the team reflects on how to become more effective, then tunes and adjusts its behaviour accordingly

I choose to point out those because their format does not leave room for debate. The active form of the verbs is used and it is not a matter of “should” or “could”, but “must”, “is”, “reflects”, “tunes”, “adjusts”. As if the authors had made their mind around all this a long time ago. 

And actually, this is what they pretend. In the introduction, on the first page of the manifesto, we find the root of their certainties: “We are uncovering better ways of developing software by doing it and helping others do it”.  Note the present progressive form though, which suggests that they acknowledge that their journey towards better ways of developing software is not over.

They root their certainties into their experience in the field. The authors who wrote the Agile manifesto did not write it right out of university. They had already spent a whole career in the IT industry. And it was not one or two friends speaking as one brain neither, but distinct professionals with different opinions about what people should focus on. And after that they continued to challenge each other. As an evidence of this, consider the letter[1] that Martin Fowler wrote in 2009 about flaccid Scrum which led Ken Schwaber to create scrum.org[2].

In this letter, Martin emphasizes the need for good technical practices and Extreme Programming as a relevant starting point.

This is where we find Test-Driven development (TDD) in the first circle.

How does TDD help with the promise of Agile?

The key here is behind the sustainable pace idea. One team could rely on manual testing during one iteration or two, but what happens after 14 iterations, after 42 iterations? What if the manual regression testing eats all the iteration? You end up with a dead product that you can not extend anymore and the promise of Agile is broken. If you are able to create automated tests that run fast, then you avoid this dead end.

Test-Driven Development usually comes with automated tests. So when you write your tests first, your regression tests come for free and you avoid the above dead end.

Test-Driven development has been described a lot and you might find several versions of it. Usually you will find at least 3 steps: Test, Code, Refactor.

Common questions: until when do I refactor? When do I stop refactoring?

When I refactor I make the code ready so that I can green the next test very fast. In real life, I might not even know what the next test will be. Coding-dojos are about practising to take advantage of this practise in the "real world" where uncertainty is the rule. Ideally, I refactor to be ready to welcome ...anything. "Welcome change even late in the development" should remind you something. Refactor until you are ready to welcome change, until you trust that your velocity will stay stable.

When I design/write test, I'm identifying what I need from that software. In real life, I might have to collaborate with a customer (!) to identify what we need to build. He/She might be very unclear about what he/she needs. When we know in our brain what we need, we identify maybe a list of tests, we write a test, designing at the same time the architecture that we need. 

When I make the code pass, I'm "authorized" to write any crapy code I need to green the test (yes even copy/paste code).

You probably act more like a Professional during the Test and Refactor steps than in the Code step.

What if software developers were hired for their ability to write tests and refactor code, rather then for their ability to write code?


People doing sport practice every day, in order to be better during the next competition. Your favourite hockey team continue to practice even when competition happens every day, fine tuning anything that could help them to be better.

How often do you practice your software development skills and let the competition aside for a moment?

Practising coding katas solo is relevant of course. Creating spaces for the team to share and learn together is critical to create a foundation for the team to build on when time for competition comes back.

Consider coding dojos, pair-programming, mob-programming. Display code on a screen, refactor code in groups, compare your favourite code smells, practice your ability to identify tough code smells like DivergentChange or ShotgunSurgery[3], do a code challenge with your team… and start over!


[1]: https://martinfowler.com/bliki/FlaccidScrum.html
[2]:https://www.scrum.org/about
[3]:https://refactoring.guru/refactoring/smells



