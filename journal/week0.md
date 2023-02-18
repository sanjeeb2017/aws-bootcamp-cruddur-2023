# Week 0 — Billing and Architecture
This journal contains the Week-0 details for AWS Boot camp. This will provide step by step approach for someone to start with AWS cloud journey. I will update and refine the details with time.

In the first week, we are going to cover the below topics.

1. All Pre-requisites required for setting up the development environment for the boot camp. This will help in praticing and developing all codes down the line. This is super important for all of us.
2. Create budgets and setting up the billing alram in AWS. There are lots of free services available in AWS and some of them are NOT covered in Free tier. So managing cost is very important in cloud. Creating your own budget and set up billing alram will help in getting alert when you have cross your defined estimation.
3. Security best pratices to be followed in AWS cloud environments. Security is very important and there is zero tolerance in security. So we have to follow some best practices while setting up the account in AWS, creating users and assign permissions or policies.

**This is my Summary report for Week-0**

1.	Get the detail overview of Cloud computing and understand different cloud models like PaaS (Platform as a Service), IaaS (Infrastructure as a Service) and Saas (Software as a Service)
2.	Create an account in Free tier of AWS. 
3.	Create an IAM user and group in AWS.
4.	Configure the MFA both for root user and IAM user.
5.	Register a new domain in Route 53 (It’s not free but good to have your own domain)
6.	Completed all pre-requisites require to start the boot camp journey like create github account, Discord account,  lucid account, gitpod account, configure gitpod chrome extension.
7.	Install and configure aws cli with IAM credentials and update the girpod yaml file and set the env variables.
8.	Copy the Andrew brown github template to own github account so that all weekly home challenge can be submitted.
9.	Created both Napkin and Lucid architectural diagram as per Boot camp approach.
10.	Go through Chirag’s Billing videos and understand the best practices that needs to be followed in billing like setting up budget alarms and understanding the different services cost model and free tier usages as well.
11.	Go through the security best practices from Ashish video and understand the best practices one should follow in cloud like MFA set up IAM user and root account, organizations structure set up in aws account, creating role and policies and follow the least privilege principles.

Here are my understanding on Billing and Architecture.

1. Napkin Diagram /Lucid Diagram : 
 For any problem statement, it is very important to understand the requirement first and start present the architeture in a Napkin or conceptual diagram. For aws boot camp, For the micro blogging site, we created a Napkin diagram, My Napkin diagram is:
<img width="347" alt="image" src="https://user-images.githubusercontent.com/24868114/219665613-687dd046-f904-4d83-bc69-4b381b938efd.png">

The conceptual diagram can be built via different tools, one of the online free tool is Lucid diagram, my Lucid diagram can be found in the below link

https://lucid.app/lucidchart/5bee033a-f23f-40f1-9477-17c0ec651c18/edit?viewport_loc=-58%2C53%2C1421%2C614%2C0_0&invitationId=inv_88620064-1ed8-4111-ac16-0708bbcc3e17

This is an incremental approach and slowly the final logical and techincal architecture diagram will be created.

2. Billing : Managing cost is very critical and important pillar in cloud. Some of the best pratices to manage the cost are
-- Create tags for each resource. This will help in understanding the usage and cost estimation.
-- Create billing alram and put threshold when limit reach to 80% ( approx), this will help in managing overall cost of the project.
-- Proactive measures need to be taken to understand the resource usage and automation needs to be put if a resource are not in used state. For example, if an ec2 instance is not used, better to stop it to save the cost.
-- AWS has differnt cost model w.r.t services and region. So before creating any environment, better to calculate cost estimation using AWS calculator ( Link - https://calculator.aws/#/)
-- It is highly recommended to review the cost report in regular interval to understand the usages of each service and its contribution towards to the overall cost.

**Notes**
1. It is very important to set up MFA for root user and create another user with admin privilage for regular activity. This is my MFA set up screenshot.
<img width="643" alt="image" src="https://user-images.githubusercontent.com/24868114/219669827-7656c708-b575-4a5f-802d-b29a128deb2f.png">
2.Create IAM groups and assign users to the IAM groups. Manage IAM policies at IAM group level.
<img width="602" alt="image" src="https://user-images.githubusercontent.com/24868114/219670217-3fda4ab6-165e-431c-9059-2bb33b805b1d.png">
3. If there is any requirement to host website, book a domain name . In my case, i used Route 53 for my domain name. A statis website is coming soon :)
<img width="599" alt="image" src="https://user-images.githubusercontent.com/24868114/219670614-43b3e4da-4b13-43b5-8a6a-e88cbe110e48.png">
4. It is very important to notified when there are any issues in AWS services, created a SNS topic ( see below) and create an event bridge to get notified.
<img width="521" alt="image" src="https://user-images.githubusercontent.com/24868114/219671180-9c84756c-68a7-482e-a0ad-e92708f0777f.png">

<img width="562" alt="image" src="https://user-images.githubusercontent.com/24868114/219671230-d8472279-6e03-4ad6-81a1-8c3f0545c278.png">

5. Cloudshell is an online development and operational environment in AWS where user can create small development codes. Cloudshell is NOT enable for all aws regions, before using it, please check whether cloudshell is available for your region or not. In my case, i check my security crdentials using cloudshell.
<img width="379" alt="image" src="https://user-images.githubusercontent.com/24868114/219671794-6983ef91-2e98-41d3-8234-8e7a69856e7d.png">

I already get a billing alram ( since i set up the limit to $10) and due to route 53 domain, i spent more than that, i got an email. Wow, billing alram worked.

<img width="678" alt="image" src="https://user-images.githubusercontent.com/24868114/219675955-45187e96-c370-494e-a520-9f243b2aeca5.png">


**Update**
1. It is highly recommended to set up the budget and alram via aws cli. Please see the details below.

<img width="640" alt="image" src="https://user-images.githubusercontent.com/24868114/219795385-051a8752-0427-4313-b126-935f6efa6d85.png">


