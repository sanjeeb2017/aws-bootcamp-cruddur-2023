# Week 0 — Billing and Architecture

In the week-0 of AWS boot camp I learned below topics.
1. All Pre-requisites require for setting up the environment for the boot camp.
2. Create budgets and setting up the billing alram.
3. Security best pratices to be followed in AWS cloud environments.

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




