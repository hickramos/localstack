# Wiki localstack

Docker compose: https://github.com/localstack/localstack/blob/master/docker-compose.yml

## Profile

```shell
# Configure a new profile
aws configure --profile localstack
```

## Endpoint

```shell
# Set the endpoint and profile
aws --endpoint http://localhost:4566 --profile localstack
```

## AWS Local

You can execute without need to use --endpoint and --profile.

Github: https://github.com/localstack/awscli-local

### Exemple

```shell
awslocal s3 mb s3://bucketname
```

## Examples

Examples using AWS-CLI and Localstack

### S3

```shell
# Make a bucket
aws --endpoint http://localhost:4566 --profile localstack s3 mb s3://bucketname

# List files from a bucket
aws --endpoint http://localhost:4566 --profile localstack s3 ls s3://bucketname

# Copy a file to bucket
aws --endpoint http://localhost:4566 --profile localstack s3 cp {file_path} s3://bucketname

# Download a file from a bucket
aws --endpoint http://localhost:4566 --profile localstack s3 cp s3://bucketname/{file_name} .
```

### Parameter Store

```shell
# Create a new parameter on Parameter Store
aws --endpoint http://localhost:4566 --profile localstack ssm put-parameter --name "/config/spring-boot-localstack_localstack/helloWorld" --value "Hello World Parameter Store" --type String
```