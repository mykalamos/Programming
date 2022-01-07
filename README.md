# Agile

Agile has been proposed as an alternative to the Waterfall development process where design and delivery are serially executed steps.

This suffered from frequent failures. Issues with software delivered atomically into Production at the end of the project would include it

1. Not working - i.e. not doing what the developers wanted
1. Not delivering i.e. not doing what the customer wanted but rather what the developer thought the customer wanted
1. Failing non-functional requirements e.g. performance

## Agile Manifesto
https://agilemanifesto.org/

We are uncovering better ways of developing software by doing it and helping others do it.

Through this work we have come to value:

| | Value | | Greater Value |
| --- | --- | --- | --- |
| A1 | Individuals and interactions | over | Processes and tools |
| A2 | Working software | over | Comprehensive documentation |
| A3 | Customer collaboration | over | Contract negotiation |
| A4 | Responding to change | over | Following a plan |

That is, while there is value in the items on the right, we value the items on the left more.

### My Comments
The articles listed above establish an important hierarchy of values.
* A1 and A3 emphasise the engagement of individuals (which is elaborated further in the Agile Principles below)
* A2 seems like an odd juxtapostion to us now but perhaps reflecting the old days when user manuals were more in vogue.
* A4 relates to A3 and the increased iterative flow of information between customer and delivery team. As a general point it clearly addresses the issue of requirement refinement but how the nature of that response is determined requires nuance (more below).

### Agile Manifesto Principles

| | Principle |
| --- | --- |
| AP1 | Our highest priority is to satisfy the customer through early and continuous delivery of valuable software.  |
| AP2 | Welcome changing requirements, even late in development. Agile processes harness change for the customer's competitive advantage. |
| AP3 | Deliver working software frequently, from a couple of weeks to a couple of months, with a preference to the shorter timescale. |
| AP4 | Business people and developers must work together daily throughout the project. |
| AP5 | Build projects around motivated individuals. Give them the environment and support they need, and trust them to get the job done. |
| AP6 | The most efficient and effective method of conveying information to and within a development team is face-to-face conversation. |
| AP7 | Working software is the primary measure of progress. |
| AP8 | Agile processes promote sustainable development. The sponsors, developers, and users should be able to maintain a constant pace indefinitely. |
| AP9 | Continuous attention to technical excellence and good design enhances agility. |
| AP10 | Simplicity--the art of maximizing the amount of work not done--is essential. |
| AP11 | The best architectures, requirements, and designs emerge from self-organizing teams. |
| AP12 | At regular intervals, the team reflects on how to become more effective, then tunes and adjusts its behavior accordingly. |

### My Comments on the Principles
* AP1,AP3 reflect the need to integrate as soon as possible which is epecially important for complex systems composed of multiple services to minimise risk later on.
* AP2 is more controversial. 'Welcoming' change is not the same as accepting it. A4 talks about responding to change and this is often reflected in Agile implementations such as Scrum where a backlog is used. Change often is very expensive in terms of development resources especially when an expectation has been changed and code has been developed upon that.
* AP4 is again controversial. Particular types of business and delivery models might benefit from this. It will depend on what level the engagement exists but context switching for developers is cognitively expensive (and therefore financially so).
* AP6 reflects pre-pandemic/wfh thinking and will depend on the type of information being conveyed. Often a hybrid approach with documents provided first and discussion to follow is more efficient. Meetings can often descend into unproductive free for alls.
* AP7 is controversial and there is a tension with AP9. THere is always a balance to made between quality and delivery with techincal debt accumulation and repayment the price. So long as this circle is acknowledged the two principles can co-exist.
* AP8 - constroversial. Sustainable development addressses the issues of burnout but sometimes scaling up and down output is more appropriate.
* AP10 - YAGNI. Absolutely.
* AP11 - Controversial. Lots of good ideas emerge from iterative development but senior developers should have a good idea of target architectures before significant work takes place. That does not preclude prototyping. Self organisation also assumes a particular type of informed well motivated developer that is not always available.
* AP12 - yes. Often implemented  as sprint retrospectives.

### My Comments on the Practice
* Agile is often used to justify no up-front design. THis encourages stream of consciousness programming that can be very inefficient. Agile merely suggests that you dont do all your design before you start writing any code. Developers thinking about the problem divorced from their keyboards is a very valuable abstraction process.
* Agile teams should be inherently democratic and this poses several problems with individual developer obsessions and the conflict that ensures therein. Opinionated developers empowered to drive change require a strong oversight culture that could be at odds with the anarchic 'self-organisation' principle.
