#### Deploy Alexa skill
1. Provide values for `alexa_parameters.json`
2. Execute `alexa_cloudformation.yml`
  ```
  aws cloudformation create-stack \
  --stack-name solutions-architect-alexa-skill \
  --template-body file://alexa_cloudformation.yml \
  --parameters file://alexa_parameters.json
  ```

#### Deploy Lambda function
1. Provide values for `aws_parameters.json`
2. Execute `aws_cloudformation.yml`
  ```
  aws cloudformation create-stack \
  --stack-name solutions-architect-lambda-function \
  --template-body file://aws_cloudformation.yml \
  --parameters file://aws_parameters.json \
  --capabilities CAPABILITY_NAMED_IAM
  ```
3. Check on the execution status either via CLI or console


#### Helpful reminders
Package the Lambda code
```
cd lambda && zip lambda.zip lambda_function.py setup.cfg && mv lambda.zip ../ && cd ../
```
