# Infrastructure as a code

To start the stack creation with parameters
aws cloudformation create-stack --stack-name myvpcwithparam --template-body file://Iaas-Code.yaml --parameters file://param.json