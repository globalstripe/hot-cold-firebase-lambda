# hot-cold-firebase-lambda

AWS Lambda Function example to detect cold or hot state.

In this example - we need to skip re-initializing the firebase connection and db object create - if the function is 'HOT'

Global code - defined before the async handler function is only executed once, when the lambda cold starts,  The handler code executes when the function is 'hot'

So loading the libraries for example.

In other implementations we do the firebase config on the global area.

In the example we need to call an async function to retrieve the Firebase ServiceAccount details from SecretsManager.

Ideally you would do that once ... in the global area ... but you cant await a response in a function call from the global area.

Top level async in Lambda would fix this!

This has been a fascinating topic to research, and a nerve-wrecking one to debug :) 
