# Infrastructure as a code

To start the stack creation with parameters
aws cloudformation create-stack --stack-name myvpcwithparam --template-body file://Iaas-Code.yaml --parameters file://param.json --capabilities CAPABILITY_NAMED_IAM

To delete the stack
aws cloudformation delete-stack --stack-name myvpcwithparam --profile harsh-prod


# Assignment 5
aws --profile=harsh-dev cloudformation create-stack --stack-name myVpc --parameters ParameterKey=imageId,ParameterValue=ami-08c40ec9ead489470 ParameterKey=envName,ParameterValue=dev --template-body file://csye6225-infra.yml --capabilities CAPABILITY_NAMED_IAM

# Assignment 6
aws --profile=harsh-dev cloudformation create-stack --stack-name myVpc --parameters ParameterKey=imageId,ParameterValue=ami-08c40ec9ead489470 ParameterKey=envName,ParameterValue=dev ParameterKey=DomainName,ParameterValue=dev.harshshah.me. --template-body file://csye6225-infra.yml --capabilities CAPABILITY_NAMED_IAM


# Assignment 9
aws --profile=harsh-root cloudformation create-stack --stack-name myVpc --parameters ParameterKey=imageId,ParameterValue=ami-09a83ecebc5d3618a ParameterKey=envName,ParameterValue=dev ParameterKey=DomainName,ParameterValue=harshshah.me. --template-body file://csye6225-infra.yaml --capabilities CAPABILITY_NAMED_IAM

aws --profile=harsh-root ec2 create-launch-template-version --launch-template-name LaunchTemplate --version-description version2 --source-version 1 --launch-template-data "ImageId=ami-08b80f138ceb259dc"

aws --profile=harsh-root autoscaling update-auto-scaling-group --auto-scaling-group-name myVpc-auto-scaling-group --launch-template LaunchTemplateName=LaunchTemplate,Version='2'

aws --profile=harsh-root autoscaling start-instance-refresh --auto-scaling-group-name myVpc-auto-scaling-group

aws acm import-certificate --certificate fileb://Certificate.pem
--certificate-chain fileb://CertificateChain.pem
--private-key fileb://PrivateKey.pem


