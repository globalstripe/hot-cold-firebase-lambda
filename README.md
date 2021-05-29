# hot-cold-firebase-lambda

AWS Lambda Function example to detect cold or hot state.

In this example - we need to skip re-initializing the firebase connection and db object create - if the function is 'HOT'
