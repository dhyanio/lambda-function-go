# lambda-function-go
AWS Lambda Func with Beautifull Golang.

## Events

Best way to provide the responses that the AWS API Gateway needs is to install the github.com/aws/aws-lambda-go/events package
This is a AWS Native API Gateway evernts handler for Golang requests. Two important types (APIGatewayProxyRequest and APIGatewayProxyResponse) which contain information about incoming HTTP requests and allow us to construct responses that the API Gateway understands.
```golang
type APIGatewayProxyRequest struct {
    Resource              string                        `json:"resource"` // The resource path defined in API Gateway
    Path                  string                        `json:"path"`     // The url path for the caller
    HTTPMethod            string                        `json:"httpMethod"`
    Headers               map[string]string             `json:"headers"`
    QueryStringParameters map[string]string             `json:"queryStringParameters"`
    PathParameters        map[string]string             `json:"pathParameters"`
    StageVariables        map[string]string             `json:"stageVariables"`
    RequestContext        APIGatewayProxyRequestContext `json:"requestContext"`
    Body                  string                        `json:"body"`
    IsBase64Encoded       bool                          `json:"isBase64Encoded,omitempty"`
}
```

```golang
type APIGatewayProxyResponse struct {
    StatusCode      int               `json:"statusCode"`
    Headers         map[string]string `json:"headers"`
    Body            string            `json:"body"`
    IsBase64Encoded bool              `json:"isBase64Encoded,omitempty"`
}
```
