Add localstack credentials block to ~/.aws/credentials (creds don't matter)

```
[localstack]
aws_access_key_id = localstack
aws_secret_access_key = localstack
```

Add localstack profile block to ~/.aws/config
```
[profile localstack]
region = ap-southeast-2
output = json
```

Start Localstack
`docker-compose up`

Deploy the serverless stack
`serverless deploy --stage dev --profile localstack`

Invoke the step function
`serverless invoke stepf --name helloWorld --log --profile localstack --stage dev`

Invoke individual lambdas
`serverless invoke --function world --log --profile localstack --stage dev`