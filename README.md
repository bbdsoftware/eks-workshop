# EKS REFERENCE WORKSHOP
The intent of this workshop is to provide a simple starting guide to set up an EKS cluster and bootstrap it with Continuous Integration tooling , Continuous Delivery Tooling  and various other extras. 
This workshop is not intended to be a base for a production ready environment but rather serve as reference material to expand upon some tools and practise

## First Steps Setting up a clsuter
The first steps of setting regarding he set up of an eks cluster can be found in  [bbdsoftware/eks-bootstrap](https://github.com/bbdsoftware/eks-bootstrap).
This guid will cover setting up an esk cluster with an opinion ingress structure. It also provides for some extras to boot strap CI via use of the jenkins operator and CD through the use of ArgoCD as a gitops CD provider.

## Setting up an opiniated structure for CI
In the  [bbdsoftware/eks-jenkins-ci](https://github.com/bbdsoftware/eks-jenkins-ci) repo is a walk through of setting up an opinionated structure to leverage the Jenkins Operator installed in the first guid.
The guide will take you through provisioning a jenkins master and configuring it through the Jenkins Operator to load job configurations form git. This allows for a jenkins config to live as git and be updated and maintained through
source. This allows us to provision many more jenkins masters within a cluster with various configs. This also means the jenkins can be treated as cattle rather than a pet.

Please see the README.md for more details.

References: 
* https://medium.com/@Joachim8675309/devops-concepts-pets-vs-cattle-2380b5aab313
* https://jenkinsci.github.io/kubernetes-operator/
* https://kubernetes.io/docs/concepts/extend-kubernetes/operator/
* https://enterprisersproject.com/article/2019/2/kubernetes-operators-plain-english


## Setting up CD with ArgoCD

The [eks-argo-cd](https://github.com/bbdsoftware/eks-argo-cd) repo you will find and example for use with argoCD. ArgoCD provitioning is covered in the first step.  
ArgoCD is a GitOps tool for CD through GitOps. All kubernetes manifests are tracked and deployed through git as a source.
Please see the README.md for more details.

References :

* https://www.weave.works/technologies/gitops/
* https://www.cloudbees.com/gitops/what-is-gitops
* https://www.youtube.com/watch?v=4owbdHzfyMY
* https://argoproj.github.io/argo-cd/

## Reference projects and utilities

Throughout some of the guid reference will be made  to a spring boot service that is used for demo purposes.
The service can be found at [eks-dpring-boot-jenkinsop-example](https://github.com/bbdsoftware/eks-pring-boot-jenkinsop-example)
Please see the README.md for more details.

## Reference starter  utilities/library
The above reference service makes use of a spring boot based web starter found here [bbd-spring-boot-web-starter](https://github.com/bbdsoftware/bbd-spring-boot-web-starter) 
This starter is a utility library that configures the use and various tools and common cross cutting
concerns. These include swagger, metrics feature toggling , and opinionated  APi payload and Exception handling. BBD has used this utility at in various projects to facility easier
boot strapping of sporing boot based services in an opinionated fashion. 

Please see the README.md for more details.



