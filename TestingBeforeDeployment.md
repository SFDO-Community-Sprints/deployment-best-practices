---
title: Testing Before Deployment
nav_order: 4
#has_children: false
---
# Testing Before Deployment

## Summary

When administrators are deploying new features to their production environment, an important stage of the [Software Development Lifecycle](https://aws.amazon.com/what-is/sdlc/) is to test the functionality of new features before they are deployed. Testing helps ensure that the features that you build meet the required standards and specifications. Identifying defects and issues before the software is released helps to improve overall quality. This process usually involves an end user of the new feature creating dummy data and testing the functionality of [metadata](https://elements.cloud/blog/understanding-salesforce-metadata-a-guide-for-non-techies/) in a Sandbox Environment. For more information on Sandbox Environments, [refer to this article.](https://docs.google.com/document/d/15qd4DIFMleltNCkn4zbUeSQUg0-7xRL9JJTMsrmHYm4/edit)  [Regression Testing](https://www.salesforceben.com/introduction-to-regression-testing-in-salesforce/) is also essential to ensure existing features are still working when new features are developed.

### Use Cases and Test Steps

Now that you have understood the importance of testing new features before deployment, let’s dive into what the process should look like. A good place to start is by noting the different business use cases that apply to end users, with respect to the new features. The next stage is to have an end user go through the different use cases in a sandbox environment and provide feedback. These phases enable administrators to identify gaps in their build before they are deployed to a production instance. They also help the organization by identifying edge cases and bugs that should be fixed before deployment. 

### What should my test scripts look like? 

When creating test scripts, it is important to have context on who your end user is. Are they tech-savvy? Have they been working with Salesforce for over 10 years, or are they a beginner? Once you have an idea of who your target end user is, you can begin creating “test scripts” for them. 

Here is a list of important features that every test script should have and some tips on how to create them (please note that this list is not exhaustive, and can vary based on your organizations’ need):

- Business Use Cases:  
  As an end-user, how am I going to utilize this new feature/function? What are my business goals as an end user and how does it relate to this new feature/function in the build?  
  A good framework to follow is: As a \_\_\_\_(Salesforce Profile) user, I would like the ability to \_\_\_(business use case), so that I can \_\_\_\_(pain point eliminated with feature). An example is: As a fundraising user, I would like the ability to automatically convert Leads to Contacts if they respond to my email outreach, so that I can save time on administrative tasks. 

- Steps:  
  As an end user, what steps do I need to follow to utilize this new feature/function?

  In this section, you should outline the step-by-step instructions on how to utilize the new function you have built for the end users. It is always a good idea to provide a visual example for each step, such as a screenshot or a video recording. An example of test steps is as follows:   
  - Step 1: Create a new lead with your email address  
  - Step 2: Send an email to the lead using Salesforce  
  - Step 3: Check your inbox for the email and respond to it

- Expected Behaviour:  
  After following the steps outlined in the test scripts, what results should I expect to see as an end-user? 

  In this section, you should outline the expected behavior that end users should experience after following the step-by-step instructions you created. This section is important as it creates a basis for end users to provide feedback on the new feature/function that you have built. 

- User Comments and Progress:  
  Finally, it is important to have a section where users can input their feedback, provide comments on what they are experiencing during the testing phase, and sign off on the build if all is well. 

Here is a link to a template that you can use for your organization. 

### What if I don't have an end user that is available to test the functionality? 

In the event that you do not have a team member or end user that is able to test the functionality of new features before deploying, as an Admin user, you can log into Salesforce with a user that has the same profile as the end user that you are building for. Then, go through the test steps as if you were an end user. 

### Testing with permissions in mind

Having end users log in to the sandbox or using the “Login As” feature is critical as it allows you to test that the correct permissions and access have been applied. If you only test logged in as an administrator, you may hit some unexpected access issues or errors when your feature goes to production.

### Design with Testing in Mind

Before you start building your new feature, think about the testing you should conduct. In tandem with determining the requirements for a feature, determine the corresponding test scenarios and write out your test scripts. This should include both positive tests (the “happy path” and what should result), and negative tests (what happens when a user behaves unexpectedly or inputs invalid data). Negative tests could include:

* Leaving a required field blank  
* Entering letters in a field that only accepts numbers  
* Exceeding field length limits  
* Entering data that violates an existing validation rule  
* Intentionally hitting fault paths in a flow

## Key Takeaways

* Testing before deploying a change set can save your organization time and resources by identifying bugs in a sandbox environment, and rectifying them before a deployment to production. 

## Further Learning & Resources

* [Snowforce '19: 7 Principles of Testing Every Admin Should Know](https://app.pluralsight.com/library/courses/snowforce-2019-session-11/transcript)  
* [Simple concept that can reduce rework by 80%](https://elements.cloud/blog/simple-concept-that-can-reduce-rework-by-80/)  
* [6 ways to improve your debugging skills](https://www.functionize.com/blog/6-ways-to-improve-your-debugging-skills)  
* [How the Testing Manifesto is going to change development](https://www.techtarget.com/searchsoftwarequality/opinion/How-the-Testing-Manifesto-is-going-to-change-development?Offer=abt_pubpro_AI-Insider)  
* [Unit Testing on the Lightning Platform](https://trailhead.salesforce.com/content/learn/modules/unit-testing-on-the-lightning-platform)  
* [Play by Play: Salesforce Admin Essential Testing Techniques](https://app.pluralsight.com/library/courses/salesforce-admin-essential-testing-techniques/table-of-contents)  
* [Flow Testing: Step-by-Step](https://trailhead.salesforce.com/content/learn/modules/flow-testing-and-distribution)  
* [Explore Software Testing](https://trailhead.salesforce.com/content/learn/trails/explore-software-testing)  
* [User Acceptance Testing: A step-by-step guide](https://www.amazon.com/User-Acceptance-Testing-Step-Step/dp/1780171676/ref=asc_df_1780171676/?tag=hyprod-20&linkCode=df0&hvadid=312140868236&hvpos=&hvnetw=g&hvrand=5593528594256761555&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9021744&hvtargid=pla-312584180391&psc=1)  
* [Salesforce.com Quick Login As](https://chrome.google.com/webstore/detail/salesforcecom-quick-login/dccccilgophpadpomgajjlkkioipoojh)  
* [Enable Administrator to Log in as Any User](https://www.youtube.com/watch?v=Ppji7hjc8Ks)  
* [Scribehow: Create Step-by-step guides](http://www.scribehow.com)  
* [Data Generation Toolkit](https://github.com/SFDO-Community-Sprints/DataGenerationToolkit)  
* [Video Documentation](https://www.guidde.com/)  
* [Copado Salesforce Testing](https://www.copado.com/product-detail/salesforce-testing)  
* [Provar Salesforce Testing Documentation](https://documentation.provar.com/documentation/)

## Author(s)

Suraj Varma  
Ashley Vogel  
John Sim

## History
_First Published: 2024-09-27_