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

Other work tools for the project

  [Create Free Github account](https://www.youtube.com/watch?v=rirBD2CZZXQ&t=150s)

  [Create Free Gitpod account](https://www.youtube.com/watch?v=yh9kz9Sh1T8&t=15s)

  [Create Lucidchat account](https://www.youtube.com/watch?v=bgFzBYLT3sU)

### Cruddur Application Conceptual Design

Lucidchart was used to create the conceptual diagram. Link to the [Conceptual Architecture](https://lucid.app/lucidchart/0229f6e3-46e0-456d-a292-654d505d063a/edit?viewport_loc=-516%2C-164%2C3180%2C1542%2C0_0&invitationId=inv_eccb8248-943a-4c52-934b-4a0de6dab244)

insert image here.....

### Cruddur Application Logical Design

Here is the Logical diagram for the Cruddur app [Logical Diagram](https://lucid.app/lucidchart/dde97c97-95e1-4f9d-9d53-4a94e92be302/edit?view_items=ijLxN77egCnL&invitationId=inv_f9d4c3a0-d9d4-498e-874d-cc9bb9927966)

Insert image here

### Security Consideration

Security is vital, therefore understanding the foundation is important. The [video](https://www.youtube.com/watch?v=4EMWBYVggQI&list=PLBfufR7vyJJ7k25byhRXJldB5AiwgNnWv&index=16) explains what needs to be known for **DAY 0** cloud security, and how to secure your AWS account.

### Spend Consideration
Explained [Here](https://www.youtube.com/watch?v=OVw3RrlP-sI&list=PLBfufR7vyJJ7k25byhRXJldB5AiwgNnWv&index=13).

#### Setting up Billing Alarms.
Navigate to billing and click the Billing Preference to setup your refered options by ticking the boxes and input your email address and save preference.

Billing preference picture here.

Specify metrics and condition:
Next is to manage Billing Alert and setup the budget feature(a new feature)
Navigate to cloudwatch, click on Alarms > click on in alarm > click on create Alarm > select metrics > click billing > and then Next. Input the Metric you want, the condition of choice, Estimated charge desired before triggered and the amount in figures (USD) and click next

Metrics pictures

Configure actions: 
create an SNS topic , input the email address then click add notification

Picture for configure actions

Add an alarm name of choice, add description if you want and click next

Picture for add name and description

Preview and click on create alarm
Note: ensure to confirm SNS message sent to the endpoint(the email provided in the alarm setup)

Picture for Allalarms

