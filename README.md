# AWS Cloud Cost Management

I've seen both sides of arguements on whether the cloud is cheaper than on-Premise and do-it-all-yourself. 

The value proposition is different for all businesses. Dropbox saved millions of dollars by moving out of the cloud as you can read in this article:https://www.techrepublic.com/article/dropbox-saved-75m-by-dumping-the-cloud-but-your-company-wont/

The article also says 
> " If that sounds amazing, it is. It's also highly unlikely that you'll be able to get the same sort of cost savings because, well, you're not Dropbox." 

For example, for most startups, Cloud probably is the best option. Then you have companies like dropbox. That's when you host cloud on a cloud. Situation like this is when companies start to considering moving out of the cloud to save even more.

## CORE PILLARS OF COST OPTIMIZATION ( According to the AWS Cost Optimization Playbook, Jan 2018)
• Right sizing: Provisioning the right services for
given workloads.\
• Elasticity: Growing and shrinking consumption based
on volume- and time-based needs.\
• Pricing models: Using On Demand, Reserved, and
Spot Instances efectively.\
• Storage optimization: Choosing the right storage tier
for the workload.

## BEST PRACTICES FOR COST OPTIMIZATION ( According to the AWS Cost Optimization Playbook, Jan 2018)
• __Defne and enforce cost allocation tagging:__ Tagging enables the assignment of custom metadata to instances,images, and other resources. For example, resources can be categorized by owner, purpose, or environment, helpingto organize them and assign cost accountability. Tagging taxonomy and enforcement should be determined as early as possible in the adoption for cloud services.\
• __Use efective account structures:__ For many organizations,a consolidated billing strategy where all AWS accounts are paid through one master account facilitates simplifed payments, maximizes volume discounts, and makes it possible to share Reserved Instance benefts across linked accounts. AWS Organizations enables the creation of groups of AWS accounts, with central policy management and consolidated billing.\
• __Defne and use metrics:__ Set targets and review progress against them at a set cadence.\
• __Enable teams to architect for cost:__ Employ training, visualization of progress goals, and balance of incentives.\
• __Assign optimization responsibility to cloud center of excellence (CCoE):__ A CCoE is charged with overseeing the quality and cost-efectiveness of cloud transformation eforts. It can start small and evolve with the organization’s needs.Having one locus of responsibility for cloud excellence can drive greater cost and value optimization.

### AWS Cost Optimization Playbook ( Jan 2018)
https://d1.awsstatic.com/pricing/AWS_CO_Playbook_Final.pdf

# Tips to save money on your AWS bill

- EIP costs money if it's not attached to anything or is attached to a stopped EC2 instance.
- Consider buying Reserved capacity for Instances, Tables etc. You pay upfront, for big discounts. 
- Consider when you can leverage Spot Instances(They sometimes come at a 90% discount compared to on-demand instance).
- Even though reserved Instances could save you money, don't buy the wrong type or quantity. You may have to put it on Reserved Instance marketplace for sale.
- Conversely, checkout the Reserved Instance Marketplace for deals on EC2 reserved instances.
- My DynamoDB use until now has been covered by the free tier limits. But I've seen some examples where people save considerable money by moving from DynamoDB to somethings else for their data Storage. 
- Used Glacier for long term storage, Reduced reduncy storage for objects that can be reproduced.
- Use Lifecycle policies to transitions objects from S3 standard --> IA--> Glacier
- Consolidate your billing to get group discount.
- Consider Using VPC endpoints , especially if you're using NAT Gateway with a lot of traffic. Just by switiching to VPC endpoints, businesses can save thousands of dollars per months as mentioned in this article:https://bluesentryit.com/gain-real-savings-proper-cloud-setup/
-  Use Lambda to turn off dev/test environments in the weekends/evenings. 








### DynamoDB Cost tips:
https://content.nexosis.com/blog/understanding-dynamodb-costs-and-document-sizing

### S3 Cost tips:
https://blog.cloudability.com/aws-s3-understanding-cloud-storage-costs-to-save/






## Other things to consider

- Consider that with managed services like RDS  you need fewer engineers to setup a service. Your cloud cost may be higher , but you may need less engineers. 

