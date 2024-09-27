---
title: Environment Selection and Creation 
nav_order: 3
#has_children: false
---
# Environment Selection and Creation

## Summary

When making changes to your Salesforce org, you should think carefully about what environment you use to make and test your changes. 

## Detail

Salesforce Sandboxes are copies of your production org’s setup that may or may not have copies of the data from your production org. Sandboxes come with different storage capacities and refresh capabilities based on their type. Salesforce recommends making all configuration changes in a Sandbox; however, careful consideration should be taken when selecting sandboxes, as each has different strengths and weaknesses.

When starting a new effort to add new features, you should create a new sandbox – and think carefully about which type best suits your needs.

### Full Copy Sandboxes

Full-copy sandboxes contain a complete copy of your Production org’s setup and all the data in it. If you have Unlimited Edition, you get one Full Copy Sandbox with your Salesforce contract. If you have Enterprise Edition or a lower edition, you can purchase a Full Copy Sandbox at an additional cost.

Because Full Copy Sandboxes contain a complete copy of all your production data, they make excellent testing environments; they also present challenges and risks.

**Reason to use:**

* Complete replication of your Production environment and data.  
* Test changes with production data without the risk of affecting your actual data.  
* It allows for complete testing of integrations and performance and is ideal for UAT testing.  
* Supports version control and change management.

**Cons:**

* The cost may be prohibitive for small to medium organizations.  
* During testing, there is a risk of accidentally sending emails to real contacts. A validation rule could be helpful.   
* Data Security: These sandboxes contain a complete copy of your production data, creating more data security concerns.  
* No native data masking.  
* You can only refresh these sandboxes once every 30 days.

### Partial Copy Sandboxes

Partial Copy Sandboxes can contain a subset of your production data. They are included with all Enterprise or Unlimited Edition orgs for nonprofit organizations and are available for purchase with lower editions. Because they populate data automatically, they can be suitable test environments, but Salesforce's selection process is limited and can create orphaned or incomplete records that may break other processes.

**Reason to use:**

* Good for User Acceptance Testing (UAT) testing  
* You can do some integration testing, but it may require additional setup.  
* Create reusable templates to pull data from Production.  
* Quick and relatively easy to set up.

**Considerations for Partial Sandboxes:**

* Admins can’t choose which records are copied, and will need to clean data, including, but not limited to, Lookups, child records and may need to create records to ensure all processes work as intended. (consider using a seeding tool)  
* Limit of 10,000 records per record type, and 5 GB data total.  
* 1 Partial Copy sandboxes.  
* The data is not sanitized without additional services.  
* You can only refresh these once every 7 days.

### Developer and Developer Pro Sandboxes

Developer and Developer Pro Sandboxes offer the same features, but the key difference lies in the storage capacity. They do not copy any data from Production and so require a separate process to create testing data. Because they do not copy any data, they are safe to use with developers or consultants who should not see your production data. You typically have a small number of Developer Pro and a larger number of Developer sandboxes.

**Reason to use:**

* Development of new features in an isolated environment  
* Project that do not require a copy of production data  
* You can refresh these sandboxes every 24 hours

**Cons:**

* Low storage limits  
* No data records copied from production  
* No retention of Salesforce IDs besides Users, such as Record Type IDs

### What About Scratch Orgs?

You may have heard of scratch orgs, which are a more advanced tool to support creating solutions on Salesforce. They are a powerful tool, but generally most effective when working on packages or with advanced teams. If you are a solo admin, or working with just a small team this may not work for you at this time.

### Getting Changes into Production

Once your changes are complete in the sandbox, you will need to deploy the changes to another sandbox for testing, or to production.  In order to do this, you will want to ensure you have a deployment connection setup between the environments you are deploying from and to.  
Other parts of this guide provide suggestions about how to move your changes when it is time.

## Key Takeaways

* Select the right sandbox for your project  
* Using Sandboxes is a best practice and helps reduce risk.  
* Tips: Code snippet/Dataload to invalidate user email Addresses

## Further Learning & Resources

Links to external websites or documentation

* [Set Up a Sandbox in Your Salesforce Org](https://trailhead.salesforce.com/en/content/learn/modules/nonprofit-success-pack-maintenance/set-up-a-sandbox-in-your-salesforce-org?trail_id=nonprofit_fundraising)  
* [Use Sandboxes to Manage Change](https://trailhead.salesforce.com/en/content/learn/modules/nonprofit-success-pack-maintenance/set-up-a-sandbox-in-your-salesforce-org?trail_id=nonprofit_fundraising)  
* [DevOps Launchpad](https://devopslaunchpad.com/)  
* [7 Best Practices for Salesforce Sandbox Management](https://www.autorabit.com/blog/7-best-practices-for-salesforce-sandbox-management/)  
* [Best Practices for Introducing a Salesforce Organization Strategy](https://allcloud.io/blog/best-practices-for-introducing-a-salesforce-organization-strategy/)  
* [What is a Salesforce Sandbox? A Beginners Guide](https://www.salesforceben.com/salesforce-sandbox/)  
* [5 reasons to use your Salesforce Sandbox today](https://www.simplus.com/5-reasons-to-use-your-salesforce-sandbox-today/)  
* [Determine Which Application Lifecycle Management Model Is Right for You](https://trailhead.salesforce.com/en/content/learn/trails/determine-which-application-lifecycle-management-model-is-right-for-you)  
* [What are Preview and Non-Preview Sandboxes?](https://help.salesforce.com/s/articleView?id=sf.data_sandbox_preview.htm&type=5)  
* [Sandbox Setup Considerations](https://help.salesforce.com/s/articleView?id=sf.data_sandbox_implementation_tips.htm&type=5)   
* [Copado Academy DevOps Training and Certification](https://success.copado.com/s/my-learning?language=en_US)  
* [Provar Salesforce Testing and Documentation](https://documentation.provar.com/documentation/)  
* [Free Google Sheets & Excel Salesforce Integration and Data Migration](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N4V00000GYgWXUA1&other_source=Web)  
* [Good tool for mass cleaning up data](https://www.xappex.com/xl-connector-salesforce-excel-connector/) \- free for NonProfits XL-Connector  
* [Connected App to Enable Users to Easily Log Into Sandboxes Directly from Production with One Click](https://www.youtube.com/watch?v=IZerw-flRHM&list=PLY6BOTuWMxwi1LdE72XFRB9a-ezkWX_8w&index=19&t=615s)  
* [Deployment: Special Behaviors](https://help.salesforce.com/s/articleView?language=en_US&id=sf.deploy_special_behavior.htm&type=5)

## Authors(s)

Alrick Bloomfield  
Aaron Crosman  
Jordyn Jaffer  
Heath Parks  
John Sim  
Ashley Vogel  
Suraj Varma

## History
_First Published: 2024-09-07_