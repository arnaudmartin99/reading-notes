# Error handling
We are responsible for our code even when errors happen because of abnormal input or failing devices.
But error handling shouldn't obfuscate code.
## Exceptions
- Prefer exceptions to return codes: handling a return code can be forgotten by the callee and above all, calling code is cleaner with exceptions because error handling is separated from the happy path
- Write try-catch-finally first with tests about exceptions in a TDD-style to help maintain the transaction nature of the scope
## Exception design
- Prefer unchecked exceptions. Checked exceptions (written in the signature of the function) break open/closed principle and encapsulation: higher level functions know about lower-level functions implementation details
- Provide context with exceptions: strack trace is not sufficient to know the intent of the operation that failed
- Define exception classe in terms of a caller's need: how they are caught is the most important
- Wrap APIs to redefine exceptions, minimize dependencies on third party code or change its design
## Avoid
- Using exceptions when part of the normal flow: if you don't need to stop the execution of the flow, maybe you should use a special case pattern.
- Returning null: returning a special case object or throwing an exception is preferable
- Passing null: there is no good way to handle null in the callee function