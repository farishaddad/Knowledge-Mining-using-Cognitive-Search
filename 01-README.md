#Azure Cognitive Search Workshop - Building an Enterprise Cognitive Search Solution

##Welcome 
Azure Cognitive Search is a new enrichment pipeline that allows you to find rich structured information from documents. This one day training will focus on hands-on activities that develop proficiency on Cognitive Search, an AI-oriented product announced on [Microsoft Build 2018](https://www.microsoft.com/en-us/build). These labs assume an introductory to intermediate knowledge of [Visual Studio](https://www.visualstudio.com/vs/community/), [Azure Portal](https://portal.azure.com), [Azure Functions](https://azure.microsoft.com/en-us/services/functions/) and [Azure Search](https://azure.microsoft.com/en-us/services/search/). If this is not your case, we have quick start materials in the pre-requisites section of this training.

##Goals
Today we will focus on hands-on activities to learn how to create a Cognitive Search solution for all types of business documents. The multiple languages provided documents include pdfs, docs, ppts and images. In this training you will create a cognitive data flow and the enriched information will become part of an Azure Search index. 

At the end of this workshop, you should be able to:

+ Understand what Cognitive Search is
+ Understand what this solution does and how it can be used, including the capability to process any unstructured data
+ Implement Cognitive Search enrichment pipelines
+ Learn how to search for cognitive skills from business documents
+ Provide you a tool for demos, POCs and other business scenarios

##Pre-requisites
Since this is an AI training on top of Microsoft Azure Services, there are certain things you need before we start.

1. We will use Visual Studio for some activities. This [link](https://docs.microsoft.com/en-us/visualstudio/ide/visual-studio-ide) has the knowledge you need to do this workshop. 
2. Together we will create small C# applications. This [short video](https://mva.microsoft.com/en-us/training-courses/c-fundamentals-for-absolute-beginners-16169?l=Lvld4EQIC_2706218949) has the knowledge you need for this training.
3. You need a Microsoft Azure account to create the services we use in our solution. You can create a [free account](https://azure.microsoft.com/en-us/free/), use your [MSDN account](https://azure.microsoft.com/en-us/pricing/member-offers/credit-for-visual-studio-subscribers/) or use any other subscription where you have permission to create services.
4. Install [Visual Studio 2017 version 15.5](https://www.visualstudio.com/vs/) or later, including the Azure development workload.
5. You need a computer with [Postman](https://www.getpostman.com/) or [Fiddler](https://www.telerik.com/download/fiddler) installed to test the APIs we will interact with. We will use this softwares to  make REST calls to Azure Search. If these tools are new to you, see [Explore Azure Search REST APIs using Fiddler or Postman](https://docs.microsoft.com/en-us/azure/search/search-fiddler).
6. You may need quick start trainings for [Azure Functions](https://docs.microsoft.com/en-us/azure/azure-functions/) and [Azure Search](https://docs.microsoft.com/en-us/azure/search/)




##Agenda
Since you have finished the pre-requisites, let's start the training. You just need to follow the workshop structure presented below.

+ [Introduction](02-Introduction.md) - 1 hour - Cognitive Search key concepts.
+ [Solution Architecture](03-Solution-Architecture.md) - 1 hour - Diagram, use cases, deployment options and costs.
+ [Solution Architecture](04-Environment-Creation.md) - 1 hour - Using Azure Portal, we will create the services we need fo the workshop.
+ [Lab 1](05-Lab-1.md) - 2 hours - Create a Cognitive Search Enrichment Process.
+ [Lab 2](06-Lab-2.md) - 1 hour - Create an extended Cognitive Search Skill and add it to the process.
+ [Lab 3](07-Lab-3.md) - 2 hours - Create a Cognitive Search **Custom** Skill and add it to the process.


##Clean up resources
If you don't want to keep the solution up and running for future use, you should get rid of the all environment. Assuming that you created all services in the same resource group, the fastest way to clean up is by deleting it. This will permanently remove the Azure Search service, the Azure Function app and Azure Blob service. Including the services and any stored content that you created for this workshop. In the portal, the resource group name is on the Overview page of each service.


##Useful Links
+ [Microsoft AI School](https://aischool.microsoft.com/learning-paths)
+ [Microsoft Analytics School](https://learnanalytics.microsoft.com/) 
+ [Microsoft AI Platform](https://www.microsoft.com/en-us/ai)
+ [Azure Search](https://docs.microsoft.com/en-us/azure/search/search-what-is-azure-search)
+ [Cognitive Search Official Demo - JFK Files](https://jfk-demo.azurewebsites.net/)
+ [Cognitive Search Official Code - JFK Files](https://github.com/Microsoft/AzureSearch_JFK_Files)
+ [How to rebuild an Azure Search Index](https://docs.microsoft.com/en-us/rest/api/searchservice/addupdate-or-delete-documents)
+ [Using Fiddle or Postman for REST API calls](https://docs.microsoft.com/en-us/azure/search/search-fiddler)

##Collaboration
We appreciate your collaboration. The code and the data are free to be used as you need. You can clone the github repo or download the solution. If you make any improvement in the workshop, you can make a pull request on GitHub that we will analyze. Feedbacks and suggestions are welcome, just send us an email at rsouza1974@outlook.com .

#Thank you!

