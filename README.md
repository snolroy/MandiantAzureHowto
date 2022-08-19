# MandiantAzureHowto

## Steps to fire up and start a Azure Red Team Attack and Detect Workshop

1- Go to https://signup.microsoft.com/get-started/signup?products=101bde18-5ffb-4d79-a47b-f5b2c62525b3&culture=en-us&country=US&ali=1 and sign up for a Microsoft E5 trial account

2- Go under Subscrioptions on your acccount and add a Free trial subscription as shown below.(A cc will be required)
    <img width="1242" alt="Screen Shot 2022-08-18 at 10 06 02 PM" src="https://user-images.githubusercontent.com/111548571/185527023-582f14f9-79d4-4d30-8b74-df6af72df37c.png">

3- Install Terraform following the steps described in the following link:
 https://learn.hashicorp.com/tutorials/terraform/install-cli
 
 The steps described in the previous link is for Mac users. You might need to change the OS and install appropriate version. 
 
4- Go to your terminal once Terraform is installed and issue the following commands :

```
az login

```

You will see a log in page pop-up. Enter your Azure creds you created in the steps above.

```
git clone https://github.com/mandiant/Azure_Workshop.git

cd Azure_Workshop

cd kc1
```
5- Open the kc1 folder in your Desktop where the repo was cloned and navigate to and open the kc1.tf file with either TexEdit on Mac or Notepad on Windows. Next, change XXXXXXX in the code below with your IP address
{
start_ip_address    = "XXXXXXX
  end_ip_address    = "XXXXXX"
}

6- Go back to your terminal and issue the following commands: 

```
terraform init
terraform validate
terraform plan -out kc1.tfplan

```
Enter the domain listed on your Azure account and enter strong Passwords when asked to enter password for the accounts that wull be created. 

7- Next, issue the following command: 

```
terraform apply kc1.tfplan

```
Once the command above is issued, the resources and users in the terraform doc would be created and reflected in your Azure account. 

8- Next perform the Kill-Chain #1:

**Objective: Gain access to the Customers PII data.**

Solutions: The full attack path solutions can be found in kc1/kc1_solution.txt

