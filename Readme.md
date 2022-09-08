

Deploy individual templates:

aws cloudformation create-stack --stack-name lambda-s3 --template-body file://LambdaS3/template.yaml --capabilities CAPABILITY_NAMED_IAM --region us-east-1 --profile acloudguru

aws cloudformation create-stack --stack-name VPC --template-body file://VPC/template.yaml --capabilities CAPABILITY_NAMED_IAM --region us-east-1 --profile acloudguru

Delete individual stacks:
aws cloudformation delete-stack --stack-name vpc --profile acloudguru
aws cloudformation delete-stack --stack-name lambda-s3 --profile acloudguru

Create a nested cloud formation template:
aws s3 mb s3://nestedstackscf1612 

aws cloudformation package --template-file template.yaml --output-template packaged.yaml --s3-bucket nestedstackscf1612 --profile acloudguru

Deploy a nested cloud formation template:
aws cloudformation deploy --template-file "C:\Users\gsarup\Documents\Documents\Cloud Formation Deep Dive\Team 3\packaged.yaml" --stack-name team3 --capabilities CAPABILITY_NAMED_IAM --profile acloudguru

