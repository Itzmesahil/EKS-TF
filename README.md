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

