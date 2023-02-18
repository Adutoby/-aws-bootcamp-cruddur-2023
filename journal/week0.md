# Week 0 — Billing and Architecturals
Week 0 was focused on the core prerequisites, which included
 - Installation of work tools 
 - Setting up our work environments (AWS, Github, Gitpod, etc)
 - Aws account creation
 - Aws user account creation
 - Security
 - Spending
   - Setting up billing alarm 
   - Budget creation on aws 
 - Gitpod and extension on Github
 - AWS Secret generation and setting up environment Variable on Gitpod
 - Application overview, and project persona 
 - Application conceptual Design (Using Lucidchat)
 - Application Logical Design (Using Lucidchat)
 
## Installation of work tools

  ### Setting up Your AWS account.

The cloud platform for the bootcamp is AWS, the major reason why an AWS account is needed. Refer to [Create free AWS account](https://www.youtube.com/watch?v=uZT8dA3G-S4&t=73s)

[Generate AWS credentials](https://www.youtube.com/watch?v=OdUnNuKylHg&list=PLBfufR7vyJJ7k25byhRXJldB5AiwgNnWv&index=14)

Other work tools for the project

  [Create Free Github account](https://www.youtube.com/watch?v=rirBD2CZZXQ&t=150s)

  [Create Free Gitpod account](https://www.youtube.com/watch?v=yh9kz9Sh1T8&t=15s)

  [Create Lucidchat account](https://www.youtube.com/watch?v=bgFzBYLT3sU)

### Cruddur Application Conceptual Design

Lucid charts was used to create the conceptual diagram. Link to the [Conceptual Architecture](https://lucid.app/lucidchart/0229f6e3-46e0-456d-a292-654d505d063a/edit?viewport_loc=-516%2C-164%2C3180%2C1542%2C0_0&invitationId=inv_eccb8248-943a-4c52-934b-4a0de6dab244)

![](https://github.com/Adutoby/aws-bootcamp-cruddur-2023/blob/main/_docs/assets/Week0_Images/conceptual_architecture.png)

### Cruddur Application Logical Design

Here is the Logical diagram for the Cruddur app [Logical Diagram](https://lucid.app/lucidchart/dde97c97-95e1-4f9d-9d53-4a94e92be302/edit?view_items=ijLxN77egCnL&invitationId=inv_f9d4c3a0-d9d4-498e-874d-cc9bb9927966)

![](https://github.com/Adutoby/aws-bootcamp-cruddur-2023/blob/main/_docs/assets/Week0_Images/logical_Architecture.png)

### Security Consideration

Security is vital, therefore understanding the foundation is important. The [video](https://www.youtube.com/watch?v=4EMWBYVggQI&list=PLBfufR7vyJJ7k25byhRXJldB5AiwgNnWv&index=16) explains what needs to be known for **DAY 0** cloud security, and how to secure your AWS account.

### Spend Consideration
Explained [Here](https://www.youtube.com/watch?v=OVw3RrlP-sI&list=PLBfufR7vyJJ7k25byhRXJldB5AiwgNnWv&index=13).

#### Setting up Billing Alarms.
Navigate to billing in your root account and click the Billing Preference to setup your refered options by ticking the boxes and input your email address and save preference.

![](https://github.com/Adutoby/aws-bootcamp-cruddur-2023/blob/main/_docs/assets/Week0_Images/BillingPreferencesetup.png)

**Specify metrics and condition:**

To manage **Billing Alert** 

Navigate to cloudwatch, click on Alarms > click on in alarm > click on create Alarm > select metrics > click billing > and then click Next. 
Input the Metric you want, the condition of choice, Estimated charge desired before triggered and the amount in figures (USD) and click next.

![](https://github.com/Adutoby/aws-bootcamp-cruddur-2023/blob/main/_docs/assets/Week0_Images/Configureactions.png)

Configure actions: 
create an SNS topic , input the email address then click add notification

![](https://github.com/Adutoby/aws-bootcamp-cruddur-2023/blob/main/_docs/assets/Week0_Images/Configureactions.png)

Add an alarm name of choice, add description if you want and click on next

![](https://github.com/Adutoby/aws-bootcamp-cruddur-2023/blob/main/_docs/assets/Week0_Images/Addnameanddesciption.png)

Preview and click on create alarm

Note: Ensure to confirm SNS message sent to the endpoint(the email provided in the alarm setup)

![](https://github.com/Adutoby/aws-bootcamp-cruddur-2023/blob/main/_docs/assets/Week0_Images/Allalarms.png)


#### Creating a Budget

Navigate to Budgets under the AWS Billing service in your root account and setup your preffered budget amount.

**Note**  After two free budget are setup you will be charged for additional budget setup.

![](https://github.com/Adutoby/aws-bootcamp-cruddur-2023/blob/main/_docs/assets/Week0_Images/Budgets.png)

### Install AWS CLI

Haven installed AWS Free account and the Gitpod account, we will proceed to install AWS CLI on our gitpod and configure our credentials and environment variables.

Firstly, lunch your code on gitpod

Refer to [AWS CLI Installation Instructions](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) and follow the steps executing the bash script in your gitpod code editing terminal.

Ensure to Update the `.gitpod.yml` to include the following task.

```
tasks:
  - name: aws-cli
    env:
      AWS_CLI_AUTO_PROMPT: on-partial
    init: |
      cd /workspace
      curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
      unzip awscliv2.zip
      sudo ./aws/install
      cd $THEIA_WORKSPACE_ROOT 
  ```

#### Set Env Vars

Refer to AWS documentation on how to set [Environment Variables](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-envvars.html)

Input your secret credentials generated with your user account within the ""

````
export AWS_ACCESS_KEY_ID=""
export AWS_SECRET_ACCESS_KEY=""
export AWS_DEFAULT_REGION=us-east-1
````

Set the env var for Gitpod to remember the credentials when relaunching our workspaces using the commands

```
gp env AWS_ACCESS_KEY_ID=""
gp env AWS_SECRET_ACCESS_KEY=""
gp env AWS_DEFAULT_REGION=us-east-1
```
Validate AWS CLI is working with below command

```
aws sts get-caller-identity
```
![](https://github.com/Adutoby/aws-bootcamp-cruddur-2023/blob/main/_docs/assets/Week0_Images/AWScliconfig.png)

