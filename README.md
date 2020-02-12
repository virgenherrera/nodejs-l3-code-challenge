# nodejs-l3-code-challenge
Challenge instructions:

## Before to start.
* Create a fork from this repository.
* clone your fork.
* set up as npm package.
* Install and configure the `eslint` package as well as` eslint-config-google`.
* Install the `jest` package, as well, configure it to run the tests with the"test" script.
* commit these changes under the **"01 prepare project"** message.

## service-level requirements
* Create a web service (using your preferred tool), the web service should have the following features:
  * Accept CORS requests.
  * Use gzip compression.
  * A customized (global) middleware that will analyze the request header and allow access only to requests that contain the "company-xyz-request": "ontime" header. and reject all other requests with the code of 401.
  * An error handler that will log the error in detail in a log (using console.error) and analyze the __"type"__ of error and transform it into a "JSON" response that will obey the standards proposed by RFC.

## Endpoint requirements:
* All endpoints should use the prefix `api`.
* Any error must be sent to the global handler, without forgetting to add the "type" property with the corresponding type of error.

## __GET__ endpoint `fibonacci/:iterator`
You must to develop an __GET__ endpoint `fibonacci/:iterator` that will implement the  following behaviours:
  * Validate that the segment `iterator` is a positive integer.
  * Will return an array that will contain all the fibonacci sequence numbers delimited by the `iterator` argument.

### Example Request1
```
GET /api/fibonacci/8
```

### Example Response1
```
{
    data: [0, 1, 1, 2, 3, 5, 8, 13, 21]
}
```

### Example Request2
```
GET /api/fibonacci/13
```

### Example Response1
```
{
    data: [0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233]
}
```

## __POST__ endpoint `unique`
You must to develop a __POST__ endpoint `unique` that will that will implement the following behaviours:
  * Extract the contained data from Request `body.data` amd validate that is an array of **primitive** values.
  * Will respond with an object containing the array without duplicates as well a property unique indicating if the original `body.data` was containing only unique values. e.g.

### Example Request1
```
POST /api/unique
{
    data: [1,2,3,4]
}
```

### Example Response1
```
{
    unique: true,
    data: [1,2,3,4]
}
```

### Example Request2
```
POST /api/unique
{
    data: [1,2,2,2]
}
```

### Example Response1
```
{
    unique: false,
    data: [1,2]
}
```

### Code Coverage
Code coverage should be above 55%.

### ...to end
Once you have completed the tasks of the challenge you must commit and send the changes to your fork, as well as create a pull request with your proposal.