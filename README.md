# DEPLOYING EKS-Cluster with CLOUDFORMATION Templates using AWS-CLI #

## Deploying stack for EKS-CLUSTER ##
    ```
    aws cloudformation create-stack --stack-name eks-cluster --template-body file://ekscluster.yaml --capabilities CAPABILITY_NAMED_IAM
    ```
## After Deploying Eks Cluster we deploy another stack for nodegroup ##

    ```
    aws cloudformation create-stack --stack-name eks-nodegroup --template-body file://nodegroup.yaml --capabilities CAPABILITY_NAMED_IAM
    ```

### After creation cluster we iam authenticate the aws cli and configure kubectl

  ####  Install aws-iam-authenticator to Amazon EKS for MACOS

    ```
    curl -o aws-iam-authenticator https://amazon-eks.s3.us-west-2.amazonaws.com/1.19.6/2021-01-05/bin/darwin/amd64/aws-iam-authenticator
    ```
  ###  Apply execute permissions to the binary. 
    ```
    chmod +x ./aws-iam-authenticator
    ```
  #### configure kubectl##

    ```
    aws eks --region us-east-1 update-kubeconfig --name ControlPlane-esg7zdwP5IN0
    ```
### We can deploy this application in working kubernetes cluster using kubectl commands or using YAML configuration files. ###


#### Frontend ###

```
kubectl apply -f knote.yaml
```

#### Backend: ###

```
kubectl apply -f mongo.yaml
```




