# Terraform-EKS

## Install AWS CLI
```
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"

sudo apt install unzip

unzip awscliv2.zip

sudo ./aws/install

aws --version
```


### Configure AWS CLI
```
aws configure
```
`Just give Access Key and Secret Key followed by ENTER-ENTER`


## Install Kubectl
```
curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.23.6/bin/linux/amd64/kubectl

chmod +x ./kubectl

sudo mv ./kubectl /usr/local/bin/kubectl

kubectl version
```

## Install Terraform

Next, Install Terraform using the below link.
```
https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli
```

### Initialize Terraform

Clone the repository and Run `terraform init`. This will intialize the terraform environment for you and download the modules, providers and other configuration required.

### Optionally review the terraform configuration

Run `terraform plan` to see the configuration it creates when executed.

### Finally, Apply terraform configuation to create EKS cluster with VPC 

`terraform apply`

## Provide IAM role for EKS

Click on the Cluster created -> Under Access -> Click on Create access entry -> IAM principal ARN - Select the "arn:aws:iam::7*********62:root" or Click on the Notification banner that AWS gives in the Cluster page -> Click on Next -> Policy name - AmazonEKSClusterAdminPolicy -> Click on Add policy -> Now click on Next -> Click on Create 
