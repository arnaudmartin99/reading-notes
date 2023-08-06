# Unit tests
Tests are code so they need to be maintained. Therefore, they should have same standards of quality as their production code. Else, they will become a liability, then be disabled, and then refactoring the production code won't be possible.
## TDD
- Write a minimal failing unit test. Write minimal production code that passes it. Repeat
## Clean tests
- Arrange, act, assert
- Readibility: clarity, simplicity, density of expression
- Test-specific functions can help create a test-specific language
- Readibility is more important than performance for tests
- One test should test one concept, minimize the assertions
## F.I.R.S.T
- Fast: to execute them frequently
- Independent
- Repeatable: to run them in any environment
- Self-validating
- Timely: written before production code
