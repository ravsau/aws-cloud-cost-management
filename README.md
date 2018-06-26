# :cloud: AWS Cloud Cost Management :dollar:

I've seen both sides of arguements on whether the cloud is cheaper than on-Premise and do-it-all-yourself. 

The value proposition is different for all businesses. Dropbox saved millions of dollars by moving out of the cloud as you can read in this article:\
https://www.techrepublic.com/article/dropbox-saved-75m-by-dumping-the-cloud-but-your-company-wont/

The article also says 
> " If that sounds amazing, it is. It's also highly unlikely that you'll be able to get the same sort of cost savings because, well, you're not Dropbox." 

For example, for most startups, Cloud probably is the best option. Then you have companies like dropbox. That's when you host cloud on a cloud. Situation like this is when companies start to considering moving out of the cloud to save even more.

##  CORE PILLARS OF COST OPTIMIZATION ( According to the AWS Cost Optimization Playbook, Jan 2018)
• **Right sizing:** Provisioning the right services for
given workloads. Downsize instances if possible to do so while meeting performance requirements. Use Cloudwatch Metrics+ Custom Metrics( for things like Memory Utilization of an EC2 instance to gather usage insight ). Choose the right instance type according to the collected metrics and gathered insights.  Guess-->Learn-->Change and optimize\
• **Elasticity:** Growing and shrinking consumption based
on volume- and time-based needs. Turn off dev/test while not required ( weekends/nights). Use Lambda+ Cloudwatch to achieve automated scheduling start/stopping of instances [Click here for video on Lambda+Cloudwatch Events for automated scheduling](https://www.youtube.com/edit?o=U&video_id=EnClBnFARSk) \
Use Autoscaling for scaling up/down according to the demand(scheduled or as traffic grows --example : site goes viral).\
• **Pricing models:** Using On Demand, Reserved, and
Spot Instances efectively. As mentioned in the Reference video no 1: use Reserved(80%), On Demand + Spot(20%)\
• **Storage optimization:** Choosing the right storage tier
for the workload.\
• **Governance , Monitoring , Measurement:**

- **AWS Service Catalog** is a service that allows organizations to create and manage catalogs of IT services that are approved for use on AWS.
- **IAM**



## BEST PRACTICES FOR COST OPTIMIZATION ( According to the AWS Cost Optimization Playbook, Jan 2018)
• __Defne and enforce cost allocation tagging:__ Tagging enables the assignment of custom metadata to instances,images, and other resources. For example, resources can be categorized by owner, purpose, teams or environment, helping to organize them and assign cost accountability. Tagging taxonomy and enforcement should be determined as early as possible in the adoption for cloud services.\
• __Use efective account structures:__ For many organizations,a consolidated billing strategy where all AWS accounts are paid through one master account facilitates simplifed payments, maximizes volume discounts, and makes it possible to share Reserved Instance benefts across linked accounts. AWS Organizations enables the creation of groups of AWS accounts, with central policy management and consolidated billing.\
• __Defne and use metrics:__ Set targets and review progress against them at a set cadence.\
• __Enable teams to architect for cost:__ Employ training, visualization of progress goals, and balance of incentives.\
• __Assign optimization responsibility to cloud center of excellence (CCoE):__ A CCoE is charged with overseeing the quality and cost-efectiveness of cloud transformation eforts. It can start small and evolve with the organization’s needs.Having one locus of responsibility for cloud excellence can drive greater cost and value optimization.
• **Make Use of the AWS Trusted Advisor service** -- Trusted Advisor has Saved AWS Customers $500 million USD by advising on potential cost savings and reducing inefficiences in AWS resources

### AWS Cost Optimization Playbook ( Jan 2018)
https://d1.awsstatic.com/pricing/AWS_CO_Playbook_Final.pdf

# Tips to save money on your AWS bill

- Elastic IP(EIP) costs money if it's not attached to anything or is attached to a stopped EC2 instance. Even the cost per hour is tiny, it adds up. 
- Consider buying Reserved capacity for Instances, Tables etc. You pay upfront, for big discounts. 
- Consider when you can leverage Spot Instances(They sometimes come at a 90% discount compared to on-demand instance).
- Even though reserved Instances could save you money, don't buy the wrong type or quantity. You may have to put it on Reserved Instance marketplace for sale.
- Conversely, checkout the Reserved Instance Marketplace for deals on EC2 reserved instances.
- My DynamoDB use until now has been covered by the free tier limits. But I've seen some examples where people save considerable money by moving from DynamoDB to somethings else for their data Storage. Use Simple monthly calculator to find out S3 vs DynamoDB costs for stroage depending on access patterns: https://calculator.s3.amazonaws.com/index.html
- Used Glacier for long term storage, Reduced reduncy storage for objects that can be reproduced.
- Use Lifecycle policies to transitions objects from S3 standard --> IA--> Glacier
- Consolidate your billing to get group discount.
-  Use Lambda to turn off dev/test environments in the weekends/evenings. 
- Consider moving downloadable assets to cloudfront instead of letting people download from your S3 bucket. This will save costs in many cases.
- Different AWS regions have different price for the services. 

## Understand Data Transfer Costs:
- Consider Using VPC endpoints , especially if you're using NAT Gateway with a lot of traffic. Just by switiching to VPC endpoints, businesses can save thousands of dollars per months on data transfer costs as mentioned in this article:https://bluesentryit.com/gain-real-savings-proper-cloud-setup/

- Inter region Traffic: EC2 traffic cost between two AZ's is NOT free. It's free within an AZ(only if you're using private IP) . So make a good tradeoff decision considering the need for High availability and Cost minimization.

- Architect your systems so that there is minimal data transfer across AWS regions or availability zones.








### DynamoDB Cost tips:
https://content.nexosis.com/blog/understanding-dynamodb-costs-and-document-sizing

### S3 Cost tips:
https://blog.cloudability.com/aws-s3-understanding-cloud-storage-costs-to-save/






## Other things to consider

- Consider that with managed services like RDS  you need fewer engineers to setup a service. Your cloud cost may be higher , but you may need less engineers. 
- Try to go from paying for what you have --> Paying for what you need.  
- Build a culture of cost accountability



## Customer Success Stories:
1) GE Oil and gas was able to reduce their Total Cost of Ownership to 52% by using moving to the cloud and saved ~15 million USD , using the tools and using metrics to automate and optimize architectre. (See Reference 1)

### Summary
- Tag resources
- Automate
- Build a cost aware culture
- Monitor
- Measure
- Improve
- Utilize Elasticity and autoscalign and different pricing models 


### AWS Tools and services for cost management
- Simple monthly calculator: https://calculator.s3.amazonaws.com/index.html
## References:
1) AWS re:Invent 2017: Optimizing Costs as You Scale on AWS (ENT302)
https://www.youtube.com/watch?v=iOWNZqG0RN4&start_radio=1&list=RDiOWNZqG0RN4

