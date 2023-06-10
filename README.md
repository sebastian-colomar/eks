# eks

All the steps will be performed from AWS Cloud9. 
You will need an account with enough AWS privileges (AdministratorAccess will work).
For this purpose you need to create a new Access Key in your AWS IAM Security Credentials and then configure the AWS credentials in your Linux terminal:
* https://console.aws.amazon.com/iam/home
```bash
aws configure

```
Clone the remote repository:
```
git clone https://github.com/aws-samples/eks-workshop-v2.git
cd eks-workshop-v2
git checkout latest
cd terraform
sed -i s/3.19.0/5.0.0/ modules/cluster/vpc.tf

```
To initiate Terraform and create the supporting infrastructure, execute the following command:
```bash
terraform init
terraform plan

```
Make sure that you review the plan before approving the `terraform apply` command as this will make changes to your infrastructure:
```
terraform apply --auto-approve

```
If after running the Terraform script you do not see the Cloud9 instance named eks-workshop do the following:
* https://www.eksworkshop.com/docs/misc/cloud9-access

The sample application for these workshop labs mirrors a basic web store, providing practical container components for our exercises. The application is designed to imitate a typical online shopping experience.

Here's an overview of the functionalities it offers:

1. **Product Catalog**: This feature allows customers to explore various products. It lists all the available products along with their details, making it easier for the customer to find what they need.

2. **Shopping Cart**: This is where the chosen items are collected. Customers can add or remove items from their cart as per their preferences. The cart updates in real time, giving customers control over their potential purchase.

3. **Checkout Process**: Once customers are ready with their selection, they can move to the checkout process. Here they review their cart, provide shipping information, and complete the payment to finalize their order.

The goal of using this sample application is to offer a realistic environment for understanding and experimenting with container components. The variety of features mimic those you would expect to encounter in a professional development project. It serves to make the workshop exercises both educational and relatable to real-world application development.

* https://github.com/aws-containers/retail-store-sample-app
