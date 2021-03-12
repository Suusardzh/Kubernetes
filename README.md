## Deploying EKS-Cluster using CloudFormation Templates and AWS-CLI 

## Prerequisites:
- aws-cli configured
- aws-cli 
```
https://docs.aws.amazon.com/cli/latest/userguide/install-macos.html#install-macosos-bundled
```

### Deploy ```EKS-cluster``` stack
    
```    
aws cloudformation create-stack --stack-name eks-cluster --template-body file://ekscluster.yaml --capabilities CAPABILITY_NAMED_IAM
```

### Deploy ```nodegroup``` stack

```
aws cloudformation create-stack --stack-name eks-nodegroup --template-body file://nodegroup.yaml --capabilities CAPABILITY_NAMED_IAM
```


### Authentication of ```aws-cli``` and configuration of ```kubectl``` 

####  Install aws-iam-authenticator to Amazon EKS for MACOS

```
curl -o aws-iam-authenticator https://amazon-eks.s3.us-west-2.amazonaws.com/1.19.6/2021-01-05/bin/darwin/amd64/aws-iam-authenticator
```
  
####  Apply execute permissions to the binary
```
chmod +x ./aws-iam-authenticator
```

#### Configure ```kubectl```

Note: Change ```cluster-name```

```
aws eks --region us-east-1 update-kubeconfig --name <cluster-name>
```

### We can deploy this application in working ```kubernetes cluster``` using ```kubectl``` commands or using YAML configuration files. ###


  #### Frontend ###

    ```
    kubectl apply -f knote.yaml
    ```

  #### Backend: ###

    ```
    kubectl apply -f mongo.yaml
    ```

### Documentation to read ##

  ```
  https://docs.amazonaws.cn/en_us/AWSCloudFormation/latest/UserGuide/template-formats.html
  ```

  ```
  https://docs.amazonaws.cn/en_us/AWSCloudFormation/latest/UserGuide/aws-resource-ec2-security-group-egress.html
  ```

  ```
  https://docs.amazonaws.cn/en_us/eks/latest/userguide/what-is-eks.html
  ```