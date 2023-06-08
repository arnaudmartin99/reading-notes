# Functions
- should be small
- should do things that are one level of abstraction below their name
- should read from higher to lower level of abstraction
- should do something or answer something : command/query separation
- should have no side effects
- are a way to avoid code duplication
## Arguments
- Functions should have none, one or two arguments
- Function and arguments should form a verb/noun pair
- No flag arguments
- Prefer Class to output argument : report.appendFooter() is better than appendFooter(report)
## Error handling
- Prefer exceptions to error codes
- Try catch is one thing so it should be a function
## Tests
- Nobody can write such code from the first time, so:
  - Write tests
  - Write draft code
  - Refactor
## Switch
A function that handles different cases, for example with a switch statement, can be a code smell. If other functions also act differently based on theses cases, one might need to refactor them to an abstract factory that create instances of the derivatives of a Class based on the switch statement cases. So that those functions can be dispatched polymorphically through the interface.
