# how-to-implement-least-privilege-on-Azure
Step 1a: Create three resource groups. I used this command: az group create --name res-dev-code --location eastus and got this result:

<img width="920" height="266" alt="image" src="https://github.com/user-attachments/assets/71441932-6856-4acf-8bd9-71007ceb5f42" />

Repeat the process for the other two resource groups using this command: az group create --name <resource group name> --location 

Here are all three resource groups I created:

<img width="1235" height="131" alt="rcu5gz6qZv" src="https://github.com/user-attachments/assets/d4c8f66e-b4c9-4376-bfc1-12b2314f9364" 

Step 1b: Create security groups and users. I created my security groups on Microsoft Entra ID like this: Entra ID > Groups > New Group. Then fill the parameters. That gave me these three security groups: 

<img width="833" height="352" alt="FSCghoC7Qf" src="https://github.com/user-attachments/assets/c065151e-13dd-40f4-9dbb-249fd50c9e3d" />

Step 2: Create users and add them to each security group. I used this command to create a user: az ad user create --display-name "insert your preferred name" --user-principal-name "sarah@NathanHome.onmicrosoft.com --password "<a-strong-password>" --force-change-password-next-sign-in null

After that, I added a user to a security group using this command:  az ad group member add --group "Res-Prod-Database (Customer financial records)" --member-id e7d795fb-bc94-460a-a573-8cb6431e4b25

I repeated step 2 for all the users. Here's my complete user list: 

<img width="2079" height="360" alt="image" src="https://github.com/user-attachments/assets/d0503892-6d8b-4345-a5fc-764a21556c99" />

Step 3: Attach a role to one of the resource groups. I attached the contributor role to the res-dev-code resource group: 

<img width="1077" height="634" alt="3AVufDajDH" src="https://github.com/user-attachments/assets/beb35642-5bba-4c5b-afb2-1e885f5533e3" />

I attached the Contributor role to Res-prod-database resource group:

<img width="1908" height="386" alt="Wo16Ylc0Yg" src="https://github.com/user-attachments/assets/c16da011-3c42-464e-94d4-33658c9df07e" />

I also attached the reader role to the  

