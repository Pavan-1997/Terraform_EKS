# Terraform_EKS

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

![APPLY](https://github.com/Pavan-1997/Terraform-EKS/assets/32020205/a8c57bf8-256f-425b-b16b-d01d499bcf89)

![EC2](https://github.com/Pavan-1997/Terraform-EKS/assets/32020205/39f55e30-9eee-4a70-887b-366a6078ba87)

![EKS](https://github.com/Pavan-1997/Terraform-EKS/assets/32020205/aa643c5d-ef7a-4277-b088-c147cfbbe3c7)

![NODE-GROUP](https://github.com/Pavan-1997/Terraform-EKS/assets/32020205/33269273-5933-4710-93e0-f8714587fbc2)


## Provide IAM role for EKS

Click on the Cluster created -> Under Access -> Click on Create access entry -> IAM principal ARN - Select the "arn:aws:iam::7*********62:root" or Click on the Notification banner that AWS gives in the Cluster page -> Click on Next -> Policy name - AmazonEKSClusterAdminPolicy -> Click on Add policy -> Now click on Next -> Click on Create 

![RESOURCES-AFTER-ROOT](https://github.com/Pavan-1997/Terraform-EKS/assets/32020205/f2f61af3-4c11-41fd-844a-5a7296947541)

![PODS](https://github.com/Pavan-1997/Terraform-EKS/assets/32020205/956361a2-c53a-4e55-b965-665b9c9d1dd7)


## ACCESS VIA KUBECTL

```
aws eks update-kubeconfig --name <cluster-name> --region <region-name>
```
