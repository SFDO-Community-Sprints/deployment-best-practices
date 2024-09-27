---
title: Welcome 
nav_order: 1
#has_children: false
---

# Welcome

This site represents an ongoing and evolving (read: work in progress) project to simplify terminology and increase the accessibility of best practices guidance around Salesforce deployments targeted to Nonprofit organization administrators. Salesforce is vast and can be overwhelming, especially for organizations that do not have the budget for third-party tools, consultants, or dedicated internal staff.

The work represents the input of a diverse group of nonprofit administrators, end-users, consultants, and Salesforce staff, current and former, from across the globe with varied experience levels. Our best practice guidance is opinionated based on that collective experience. 

## Table of Contents

* Navigating Change Requests _(to come)_
* [Environment Selection](EnvironmentSelectionGuide.md)
* Build Phase _(to come)_
* Data Seeding _(to come)_  
* [Testing Before Deployment](TestingBeforeDeployment.md)
* Deployment _(to come)_  
* Release Management _(to come)_  
* Communication and Documentation _(to come)_

## Statement on Third-Party Apps and Tools

Many third-party solutions are excellent deployment tools. While some are open source or free, many require payment and may not be accessible to all organizations. Due to the rapid changes in the market, we will avoid linking to or describing these products here. Instead, we recommend researching third-party solutions by visiting the [Salesforce AppExchange](https://appexchange.salesforce.com/) or [Trailblazer Community](https://trailhead.salesforce.com/en/trailblazercommunity).

## Glossary

This project aims to help Nonprofit Salesforce Administrators, regardless of their years of technical experience, learn and share generally accepted best practices for keeping their Salesforce environments up to date and running smoothly. 

If you’re new to Salesforce and unfamiliar with the concepts involved in moving configuration and data around, the terms you might encounter are explained below.

### API Names

An API name is a globally unique identifier that references content paths in URLs. API stands for Application Programming Interface, which is a way for developers to send commands to Salesforce without using a graphical user interface.

### Change Set

A change set is a collection of components and metadata that can be deployed from one Salesforce Environment to another. For example, you can create and test a new object in a sandbox org, then send it to your production org using a change set. Change sets can contain only modifications you can make through the Setup menu. For example, you can’t use a change set to upload a list of contact records. [Learn more about Change-Sets here.](https://help.salesforce.com/s/articleView?id=sf.changesets.htm&type=5) 

### Deployment Connection

A [deployment connection](https://help.salesforce.com/s/articleView?id=sf.changesets_about_connection.htm&type=5) is required between two Salesforce orgs to send change sets from one org to another. You can’t create deployment connections between arbitrary orgs. Instead, you create connections between all orgs affiliated with a production org. 

### Deployment Pipeline

A pipeline defines the sequence of stages that work items progress as they go through the release lifecycle from development through to production (or some other final release stage).

The pipeline consists of pipeline stages that correspond to an individual environment.

### Environment

Development environments are full-featured Salesforce environments that you use to develop and test existing or new features and custom applications. They include Developer Edition orgs, sandboxes, and scratch orgs.

### Metadata vs Data

Data is a set of raw facts and unorganized information. Metadata is the form of data that describes these raw facts. In other words, metadata refers to how each data point interacts with other data points. An example of data is a record/file uploaded to Salesforce. In this example, metadata would be the author of the file/record and the date and time it was uploaded. You can also think of metadata as the way that primary data points interact with each other.

### Open Source Commons

The Commons brings the community together to identify, prioritize, and build solutions that make using Salesforce technology easier for nonprofits and schools. Learn more [here](https://www.salesforce.com/nonprofit/commons/). 

### Regression Testing

### Sandbox

Salesforce Sandboxes are copies of your production org’s setup that may or may not have copies of the data from your production org. Sandboxes come with different storage capacities and refresh capabilities based on their type. 

### Scratch Orgs

A [scratch org](https://developer.salesforce.com/docs/atlas.en-us.sfdx_dev.meta/sfdx_dev/sfdx_dev_scratch_orgs.htm) is a Salesforce org that is “disposable.” Unlike production, developer, or other sandboxes, a scratch org is quickly created and easily deleted. These orgs are primarily used by developers to build and test their work, but they also have utility for administrators.

### Technical Debt

Technical debt is the result of adding customizations or processes for the needs of one department or to solve one specific issue instead of strategically addressing the needs of the organization as a whole. While a little technical debt is acceptable, when debt builds up in the platform, the system becomes more complex and the performance of the platform slows down. [Learn more by clicking on this link.](https://www.apexhours.com/what-is-technical-debt/)

### Test Script

A test script is a set of instructions used to verify the functionality of a new feature/function created during the development phase of a project. Test scripts enable development teams to ensure high levels of quality during development, and provide a platform to identify any bugs or issues with their build before deployment. 

### User Acceptance Testing

User Acceptance Testing (UAT) works hand-in-hand with test scripts. This phase of a project is when the end-users test the functionality of new features created during development. This process is usually conducted through test scripts, and helps development teams ensure that their build meets the needs and requirements of the end users. 

### Version Control

## Contributors

Thank you to these individuals who contributed to this project since its inception in October 2023. _(list to come)_

## Get Involved

Want to help us develop this site? Do you have suggestions for new or updated content? Get in touch and let us know _(link to come)_. 