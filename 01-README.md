# Azure Search Workshop - Building an Enterprise Cognitive Search Solution

## Welcome 
Cognitive Search (preview) adds data extraction, natural language processing (NLP), and image processing skills to an Azure Search indexing pipeline, making previously unsearchable or unstructured content more searchable. Information created by Cognitive Search Skills, such as entity recognition or image analysis, gets added to an index in Azure Search.

This one day training will focus on hands-on activities that develop proficiency with Cognitive Search, an Azure Search AI-oriented capability announced at [Microsoft Build 2018](https://www.microsoft.com/en-us/build). These labs assume an introductory to intermediate knowledge of [Visual Studio](https://www.visualstudio.com/vs/community/), the [Azure Portal](https://portal.azure.com), [Azure Functions](https://azure.microsoft.com/en-us/services/functions/) and [Azure Search](https://azure.microsoft.com/en-us/services/search/). If you are not at that skill level, we have prerequisite materials below that you **need** to complete prior to beginning this training.

## Goals
We will focus on hands-on activities to learn how to create a Cognitive Search solution for all types of business documents. The documents include pdfs, docs, ppts and images, as well as documents with multiple languages. 
In this training, you will create a data flow that uses cognitive skills to enrich your business documents. These enrichments will become part of an Azure Search index. 

At the end of this workshop, you should have learned:

+ **What** Cognitive Search is 
+ **How** to implement this Cognitive Search Solution
+ **Why** to use this solution with demos, POCs and other business scenarios


## Prerequisites
Since this is an AI training on top of Microsoft Azure Services, before we start you need:

+ **If if you don't have prior experience:**
1. **To Read:** [Visual Studio](https://docs.microsoft.com/en-us/visualstudio/ide/visual-studio-ide) tutorial
1. **To Read:** [Azure Functions](https://docs.microsoft.com/en-us/azure/azure-functions/functions-overview) quick introduction 
1. **To Read:** [Azure Search](https://docs.microsoft.com/en-us/azure/search/search-what-is-azure-search) overview
1. **To Read:** [Using Fiddler and Postman](https://docs.microsoft.com/en-us/azure/search/search-fiddler) tutorial
1. **To Watch:** [MVA: C# Fundamentals](https://mva.microsoft.com/en-us/training-courses/c-fundamentals-for-absolute-beginners-16169?l=Lvld4EQIC_2706218949) short videos

+ **Mandatory**
1. **To Create:** You need a Microsoft Azure account to create the services we use in our solution. You can create a [free account](https://azure.microsoft.com/en-us/free/), use your [MSDN account](https://azure.microsoft.com/en-us/pricing/member-offers/credit-for-visual-studio-subscribers/) or use any other subscription where you have permission to create services.
1. **To Install:** [Visual Studio 2017](https://www.visualstudio.com/vs/) version version 15.5 or later, including the Azure development workload.
1. **To Install:** [Postman](https://www.getpostman.com/) or [Fiddler](https://www.telerik.com/download/fiddler) 

> [!TIP]
> Fiddler and Postman are used to call the Azure Search APIs we will interact with, so come to the training with one installed. If you're new to Postman/Fiddler, we recommend using Postman, as many of the screenshots and instructions are geared specifically for Postman. That being said, if Fiddler is your tool of choice or you are more comfortable with it, you shouldn't have any problems completing the lab.




## Agenda
Since you have finished the prerequisites, let's start the training. You just need to follow the workshop structure presented below.

+ [Introduction](02-Introduction.md) - 1 hour - Motivation, context, key concepts
+ [Solution Architecture](03-Solution-Architecture.md) - 1 hour - Diagram, use cases, deployment options and costs
+ [Environment Creation](04-Environment-Creation.md) - 1 hour - Using the Azure Portal, we will create the services we need fo the workshop
+ [Lab 1](05-Lab-1-Text-Skills.md) - 2 hours - Create a Cognitive Search Enrichment Process: **Text** Skills
+ [Lab 2](06-Lab-2-Image-Skills.md) - 1 hour - Create a Cognitive Search Skillset: **Image** Skills
+ [Lab 3](07-Lab-3-Custom-Skills.md) - 2 hours - Create a Cognitive Search Skillset with **Custom** Skills


## Clean up resources
If you don't want to keep the solution up and running for future use, you should get rid of the environment after the course. Assuming that you created all services in the same resource group, the fastest way to clean up is by deleting it. This will permanently remove the Azure Search service, the Azure Function app and Azure Blob service (including the services and any stored content that you created for this workshop). In the portal, the resource group name is on the Overview page of each service.


## Useful Links
+ [Microsoft AI School](https://aischool.microsoft.com/learning-paths)
+ [Microsoft Analytics School](https://learnanalytics.microsoft.com/) 
+ [Microsoft AI Platform](https://www.microsoft.com/en-us/ai)
+ [Microsoft AI Principles](https://www.microsoft.com/en-us/AI/our-approach-to-ai)
+ [Microsoft AI Ethics](https://aka.ms/ai-ethics)
+ [Microsoft AI Customer Cases](https://www.microsoft.com/en-us/ai/customer-stories)
+ [Microsoft AI Lab](https://www.ailab.microsoft.com/) **-> Released on May, 2018**
+ [Deep Learning with Data Science Virtual Machine](https://blogs.technet.microsoft.com/machinelearning/2017/11/16/on-demand-webinar-ai-development-using-data-science-vms-dsvm-deep-learning-vms-dlvm-azure-batch-ai/)
+ [Azure Search](https://docs.microsoft.com/en-us/azure/search/search-what-is-azure-search)
+ [Cognitive Search Official Demo - JFK Files](https://jfk-demo.azurewebsites.net/)
+ [Cognitive Search Official Code - JFK Files](https://github.com/Microsoft/AzureSearch_JFK_Files)
+ [How to rebuild an Azure Search Index](https://docs.microsoft.com/en-us/rest/api/searchservice/addupdate-or-delete-documents)

## Collaboration
We appreciate your collaboration. The code and the data are free to be used as you need. You can clone the GitHub repo or download the solution. If you make any improvements to the workshop, you can make a pull request on GitHub that we will analyze. Additionally, if you have any feedback, issues, or suggestions, please create an issue in the "Issues" tab.

# Thank you!

