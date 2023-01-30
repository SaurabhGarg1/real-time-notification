This repo is about setting up real time notification to the UI with source as salesforce platform event.

Note: This repo is in active development, further commits are expected.

## Setup:

1. Setup salesforce event source in aws eventbridge using this [salesforce guide](https://developer.salesforce.com/docs/platform/event-relay/guide/relay-events-section.html)

2. Setup aws sam cli with your aws account.

3. Run `sam build` and `sam deploy` to deploy the stack on aws


## Testing:

After completing setup, you can test this using below

1. create a websocket connection to the endpoint, given as a output of the setup phase. for example -

```
 wscat -c wss://abcdef123.execute-api.us-west-2.amazonaws.com/production
```

2. Create a new platform event, as mentioned in the setup [salesforce guide](https://developer.salesforce.com/docs/platform/event-relay/guide/create-cloudwatch.html) (Scroll down)

3. On successful submission of platform event, the payload is received on the terminal which created websocket connection in step 1.


### References:

1. [How to setup platform events from salesforce to AWS](https://developer.salesforce.com/docs/platform/event-relay/guide/relay-events-section.html)

2. [How to Build a serverless chat app with a WebSocket API, Lambda and DynamoDB](https://docs.aws.amazon.com/apigateway/latest/developerguide/websocket-api-chat-app.html)