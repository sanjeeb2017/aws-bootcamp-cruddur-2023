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


