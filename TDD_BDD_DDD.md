# TDD/BDD/DDD

## Summary

- TDD = Writing tests first to drive coding and design.
- BDD = Writing behavior-focused specs understandable by both business and devs.
- DDD = Modeling the software closely around business concepts and logic.

## How They Fit Together

| Concept   | Focus                             | Purpose                                         | When Used                      | Typical Artifacts                        | Who’s Involved                    |
|-----------|-----------------------------------|-------------------------------------------------|--------------------------------|------------------------------------------|----------------------------------|
| **DDD**   | Domain modeling & design          | Understand & model the core business domain     | Early in project / continuously | Domain models, entities, aggregates     | Domain experts, architects, devs |
| **BDD**   | Defining behavior & acceptance criteria | Collaborate & specify behaviors as executable scenarios | After domain modeling, before dev | Feature files (Given-When-Then), acceptance tests | Business analysts, testers, devs |
| **TDD**   | Low-level unit testing & design   | Drive code correctness & maintainability        | During coding                   | Unit tests, test cases                   | Developers                        |
