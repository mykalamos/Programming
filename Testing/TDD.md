# Test Driven Development
http://butunclebob.com/ArticleS.UncleBob.TheThreeRulesOfTdd
1. No production code unless to make a failing unit test pass.
2. No more of a unit test than is sufficient to fail
  - compilation failures are failures.
3. No more production code than is sufficient to pass the one failing unit test.

- Red Green Blue
- Velocity vs Speed
- Encourages decoupling
- Dovetails with SOLID
- Act as documentation/specification
  - Indicative examples of correct functioning

"The really effective part of TDD is the size of the cycle, not so much whether you write the test first. The reason we write the tests first is that it encourages us to keep the cycles really short."

## FIRST acronymn

| | Name | Characteristics |
| --- | --- | --- |
| F | Fast | Run quickly as part of CI/CD pipelines | 
| I | Isolated / Independent | No dependencies databases, file systems, or APIs - use mocks if necessary | 
| R | Repeatable | Must produce the same result every time | 
| S | Self-validating | Automated: Run without manual intervention | 
| T | Timely | tests are created before | 

# Definition of Unit
- The smallest testable part of an application
- Circularity of definition!
  - Some _observable_ that can be asserted

# AAA
- Act
- Arrange
- Assert

# Testing Private methods
- Factor out method to new class

# Mocking
- Only use for external dependencies e.g. I/O
- Verify expectations