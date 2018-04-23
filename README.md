# AWS Cloud Cost Management

I've seen both sides of arguements on whether the cloud is cheaper than on-Premise and do-it-all-yourself. 

The value proposition is different for all businesses. Dropbox saved millions of dollars by moving out of the cloud as you can read in this article:https://www.techrepublic.com/article/dropbox-saved-75m-by-dumping-the-cloud-but-your-company-wont/

The article also says ," If that sounds amazing, it is. It's also highly unlikely that you'll be able to get the same sort of cost savings because, well, you're not Dropbox." 

For example, for most startups, Cloud probably is the best option. Then you can companies like dropbox. That's when you host cloud on a cloud. Situation like this is when companies start to considering moving out of the cloud to save even more.



# TIPS save money on your AWS bill?

- EIP costs money if it's not attached to anything or is attached to a stopped EC2 instance.
- Consider buying Reserved capacity for Instances, Tables etc. You pay upfront, for big discounts. 
- Consider when you can leverage Spot Instances(They sometimes come at a 90% discount compared to on-demand instance).
- Even though reserved Instances could save you money, don't buy the wrong type or quantity. You may have to put it on Reserved Instance marketplace for sale.
- Conversely, checkout the Reserved Instance Marketplace for deals on EC2 reserved instances.
- My DynamoDB use until now has been covered by the free tier limits. But I've seen some examples where people save considerable money by moving from DynamoDB to somethings else for their data Storage. 
- Used Glacier for long term storage, Reduced reduncy storage for objects that can be reproduced.
- Using Cloudfront 






### DynamoDB Cost tips:
https://content.nexosis.com/blog/understanding-dynamodb-costs-and-document-sizing

### S3 Cost tips:
https://blog.cloudability.com/aws-s3-understanding-cloud-storage-costs-to-save/







## Other things to consider

- Consider that with managed services like RDS  you need fewer engineers to setup a service. Your cloud cost may be higher , but you may need less engineers. 

