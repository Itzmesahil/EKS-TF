get login with your iam role with proper permission
Change in backend file s3 bucket name and your region
-----BEGIN WITH THIS-----
https://docs.aws.amazon.com/eks/latest/userguide/install-kubectl.html
------ CMD TO EXECUTE -------
terraform fmt
terraform init
terraform plan
terraform validate
terraform apply 
terraform destroy

Check your iam user/role
aws sts get-caller-identity
--------
Add .kube config k8s
aws eks update-kubeconfig --region region-code --name my-cluster

INSTALL ARGOCD....
218  kubectl create namespace argocd
  219  kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/v2.4.7/manifests/install.yaml
  220  sudo curl --silent --location -o /usr/local/bin/argocd https://github.com/argoproj/argo-cd/releases/download/v2.4.7/argocd-linux-amd64
  221  sudo chmod +x /usr/local/bin/argocd
  222  kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "LoadBalancer"}}'
  223  export ARGOCD_SERVER=`kubectl get svc argocd-server -n argocd -o json | jq --raw-output '.status.loadBalancer.ingress[0].hostname'`
  224  export ARGO_PWD=`kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d`
  225  argocd login $ARGOCD_SERVER --username admin --password $ARGO_PWD --insecure
  kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath='{.data.password}' | base64 -d

  

