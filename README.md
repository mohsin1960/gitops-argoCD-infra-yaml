**Create 2 repos**

**CODE-REPO**
**1st** for **Application Code** and **.github/workflow/abc.yaml**
Change workflow.yaml file according to  repos, credentials and other things 

  The .github folder will be in the root of Application folder

  https://github.com/mohsin1960/gitops-argoCD   (Repo URL)
  

**INFRA-REPO**
**2nd** for the **infra (manifests)** and the Deployment part of **workflow** pointing to that repo of infra. 
  Also add the infra repo URL in the ArgoCD connectivity and in App creation. 


Video source: https://www.youtube.com/watch?v=mkz2V1Tl2H0

**Port-forward of app:** 
kubectl port-forward svc/react-app 3001:80 -n argocd


**Architecture**

Github Source (App Code) ==> Build-Code ==> Push to Docker-Hub with Tag Hash ==> Update Manifest of Infra with Latest Tag(Placed in github) ==> Argo CD connected with Infra Repo and see changes ==> Any-change in Infra Repo Trigger ArgoCD to deploy the Applications with the Latest Tag on the Cluster 


Note: ArgoCD installed in the same cluster in **argocd** namespace
