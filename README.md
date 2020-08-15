# opa-rest-api
The Open Policy Agent is an open source, general-purpose policy engine that unifies policy enforcement across the stack. OPA provides a high-level declarative language that let’s you specify policy as code and simple APIs to offload policy decision-making from your software. You can use OPA to enforce policies in microservices, Kubernetes, CI/CD pipelines, API gateways, and more.
Here we would discussed about the rest api's of opa which is super helpful when we run opa as seprate service on the kubernetes.
## Different Rest API's
Here is the specicifications of the different OPA rest api's-
#### Policy API
This policy API expose some CRUD endpoint for managing policy modules.
for list policies - 
```
curl -X GET \
  http://10.97.153.112:8181/v1/policies
```
Get a policy - 
```
curl -X GET \
  http://10.97.153.112:8181/v1/policies/policies/example.rego
```
Create or Update a policy -
```
curl -X PUT \
  http://10.97.153.112:8181/v1/policies/policies/example.rego \
  -H 'Content-Type: text/plain' \

main = msg {
  msg := sprintf("hello, %v", input.user)
}'
```
Delete a policy - 

```
curl -X DELETE \
  http://10.97.153.112:8181/v1/policies/policies/example.rego \
  -H 'Content-Type: text/plain' \

main = msg {
  msg := sprintf("hello, %v", input.user)
}'
```

#### Query API
Execute a query - 

```
curl -X POST \
  http://10.97.153.112:8181 \
  -H 'Content-Type: application/json' \

  -d '{
	"user":["alice"]
}'
```


