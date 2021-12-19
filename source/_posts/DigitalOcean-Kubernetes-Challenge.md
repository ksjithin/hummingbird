---
title: DigitalOcean Kubernetes Challenge
date: 2021-12-19 15:04:58
tags:
---
One of my friend mentioned about this [Kubernetes challenge raised by Digitalocean](https://www.digitalocean.com/community/pages/kubernetes-challenge) and i decided to give it a try. Prior to doing the challenge, i had very limited knowledge about kubernetes and helm. This challege pushed me to learn about both and was fun learning about it.

There is a list of challenges provided at the [registration form](https://docs.google.com/forms/d/e/1FAIpQLSdil-lIxbh7W08zourmlt2pMWP8Sn8y3u6hhAILR9eiqhy-Ww/viewform) and i decided to go with deploying an internal container registry challege. 

First i learned about kubernetes by refereing the following documentations. The official documentation helped me with understanding the basic terminologies used in kubernetes. Then i followed some of the tutorials from digital ocean to set up my kubernetes environment. 

https://kubernetes.io/docs/tutorials/
https://www.digitalocean.com/community/tech_talks/getting-started-with-kubernetes-on-digitalocean
https://www.digitalocean.com/community/tech_talks/how-to-deploy-your-application-or-microservice-as-a-kubernetes-deployment
https://www.digitalocean.com/community/tech_talks/deploying-microservices-as-kubernetes-daemonsets-and-jobs
https://www.digitalocean.com/community/tech_talks/how-to-use-kubernetes-services-to-expose-your-app

Then I used the following tutorial to learn and understand about HELM

https://www.digitalocean.com/community/tutorials/how-to-install-software-on-kubernetes-clusters-with-the-helm-3-package-manager

Once i understood how to use both kubernetes clusters and helm i follwed below steps to complete the deployment of harbor into my cluster. 

## Setting up the environment.
We have to set up *doctl* and *kubectl* in our personal system inorder to access the clusters and provide commands. 
We can install *doctl* following the url https://docs.digitalocean.com/reference/doctl/how-to/install/ 
Similarly setup *kubectl* as described here in the document https://www.digitalocean.com/community/cheatsheets/getting-started-with-kubernetes-a-kubectl-cheat-sheet

## Create the kubenetes cluster
First create the cluster which can be done very easily from the DigitalOcean Control Panel as describe here https://docs.digitalocean.com/products/kubernetes/how-to/create-clusters/

##  Install Trefik Ingress using Helm
This is one of the challege i faced initially. At first , i was trying to setup an nginx ingress but somehow the external IP was not getting assigned after i deploy the Harbor instance using Helm. I spend a considerable amout of time trying to troubleshoot how to fix including changing the expose type from ingress to nodeport and loadbalance. After all failed attemps i decided to give a try for Trefik Ingress . 


checking 
```sh
helm repo add traefik https://helm.traefik.io/traefik
```


```sh
helm repo update
```


```sh 
helm install traefik traefik/traefik
```


## Install Harbor using Helm
Before we install harbor using helm , we need to define some of the values in a yaml file ( you can refer my gihub repo). I've mentioned the type as ingress and disabled tls for simplicity of configuration. We need to specify the url that will be used to access the application in the file.
Once the yaml file has been created we can go ahead installing using helm with below commands.  

```sh
helm repo add harbor https://helm.goharbor.io
```

```sh
helm repo update
```

```sh
helm install my-release harbor/harbor -f values.yaml
```

Once harbor install is complete , it can be access from URL specified in the values.yaml file.

## Whats next
This challege has helped me kickstart with kubernetes and helm. In my next blog im planning to describe how to use this setup in a complete CI/CD environment by setting up a dockerized application , pushing the image into the harbor registry and deploying it using kubernetes environment. Stay Tuned !!!




