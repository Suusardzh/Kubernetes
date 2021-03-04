# EKS-Cluster 
### run command with params
```
aws cloudformation create-stack --stack-name ec2-cli --template-body file://Documents/cfn/ec2.yaml --parameters ParameterKey=SubnetType,ParameterValue=PublicSubnet
```


aws cloudformation create-stack --stack-name test --template-body file://eks-cluster-update.yaml --parameters file://eks-cluster-var.json --capabilities CAPABILITY_IAM

```
aws cloudformation create-stack --stack-name eks-cluster --template-body file://eks-template.yaml --capabilities CAPABILITY_NAMED_IAM
```

```
aws cloudformation delete-stack --stack-name eks-2 --template-body file://test.yaml --capabilities CAPABILITY_NAMED_IAM
```

```
aws cloudformation create-stack --stack-name eks-nodegroup --template-body file://eks-nodegroup.yaml --capabilities CAPABILITY_NAMED_IAM
```

We can deploy this application in working kubernetes cluster using kubectl commands or using YAML configuration files.

Frontend:

kubectl apply -f knote.yaml

Backend:

kubectl apply -f mongo.yaml

Recommended Documents for references:



