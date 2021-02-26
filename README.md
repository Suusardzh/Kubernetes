# Kubernetes
This is a simple kubernetes-based microservices application that will help you to upload an Image with Notes. It is designed as a 2 tier architecture (frontend - nodejs and backend - mongodb). This was originally developed by https://github.com/learnitguide/kubernetes-knote  and modified it for practice purpose only.

We can deploy this application in working kubernetes cluster using kubectl commands or using YAML configuration files.

Frontend:

kubectl apply -f knote.yaml

Backend:

kubectl apply -f mongo.yaml

Recommended Documents for references:

Introduction to Kubernetes - https://www.learnitguide.net/2018/08/what-is-kubernetes-learn-kubernetes.html

Setting up Kubernetes Cluster on CentOS / RedHat - https://www.learnitguide.net/2018/08/install-and-configure-kubernetes-cluster.html

Setting up Kubernetes Cluster on Ubuntu - https://www.learnitguide.net/2020/01/how-to-install-kubernetes-on-ubuntu.html

Write your First Yaml File to deploy application - https://www.learnitguide.net/2018/08/create-kubernetes-yaml-for-deployment.html

