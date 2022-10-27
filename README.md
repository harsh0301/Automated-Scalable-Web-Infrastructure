# Infrastructure as a code

To start the stack creation with parameters
aws cloudformation create-stack --stack-name myvpcwithparam --template-body file://Iaas-Code.yaml --parameters file://param.json --capabilities CAPABILITY_NAMED_IAM

To delete the stack
aws cloudformation delete-stack --stack-name myvpcwithparam --profile harsh-prod


#Assignment 5
aws --profile=harsh-dev cloudformation create-stack --stack-name myVpc --parameters ParameterKey=imageId,ParameterValue=ami-08c40ec9ead489470 ParameterKey=envName,ParameterValue=dev --template-body file://csye6225-infra.yml --capabilities CAPABILITY_NAMED_IAM
