#Azure Cognitive Search Workshop - Building an Enterprise Cognitive Search Solution

##Welcome 
Azure Cognitive Search is a new enrichment pipeline that allows you to find rich structured information from documents. This one day training will focus on hands-on activities that develop proficiency on Cognitive Search, an AI-oriented product announced on [Microsoft Build 2018](https://www.microsoft.com/en-us/build). These labs assume an introductory to intermediate knowledge of [Visual Studio](https://www.visualstudio.com/vs/community/), [Azure Portal](https://portal.azure.com), [Azure Functions](https://azure.microsoft.com/en-us/services/functions/) and [Azure Search](https://azure.microsoft.com/en-us/services/search/). If this is not your case, we have quick start materials in the pre-requisites section of this training.

##Goals - Bring Your Own Data!
Today we will focus on hands-on activities to learn how to create a Cognitive Search solution for all types of business documents. You can bring your own documents or use the provided documents that include pdfs, docs, ppts and images. In this training you will create a cognitive data flow and the enriched information will become part of an Azure Search index. 

At the end of this workshop, you should be able to:

+ Understand what Cognitive Search is
+ Configure your Cognitive Search service
+ Implement Azure Search features to provide a positive search experience inside applications
+ Configure an Azure Search service to extend your data to enable Cognitive Search
+ Build a solution that can enrich, index and search for business documents

##Pre-requisites
Since this is an AI training on top of Microsoft Azure Services, there are certain things you need before we start.

1. We will use Visual Studio for some activities. This [link](https://docs.microsoft.com/en-us/visualstudio/ide/visual-studio-ide) has the knowledge you need to do this workshop. 
2. Together we will create small C# applications. This [short video](https://mva.microsoft.com/en-us/training-courses/c-fundamentals-for-absolute-beginners-16169?l=Lvld4EQIC_2706218949) has the knowledge you need for this training.
3. You need a Microsoft Azure account to create the services we use in our solution. You can create a [free account](https://azure.microsoft.com/en-us/free/), use your [MSDN account](https://azure.microsoft.com/en-us/pricing/member-offers/credit-for-visual-studio-subscribers/) or use any other subscription where you have permission to create services.
4. Install [Visual Studio 2017 version 15.5](https://www.visualstudio.com/vs/) or later, including the Azure development workload.
5. You need a computer with [Postman](https://www.getpostman.com/) or [Fiddler](https://www.telerik.com/download/fiddler) installed to test the APIs we will interact with. We will use this softwares to  make REST calls to Azure Search. If these tools are new to you, see [Explore Azure Search REST APIs using Fiddler or Postman](search-fiddler.md).
6. You may need quick start trainings for [Azure Functions](https://docs.microsoft.com/en-us/azure/azure-functions/) and [Azure Search](https://docs.microsoft.com/en-us/azure/search/)




##Agenda
Since you have finished the pre-requisites, let's start the training. You just need to follow the workshop structure presented below.

+ [Introduction](Introduction.md) - 1 hour - Cognitive Search key concepts 
+ [Solution](Solution.md) - 1 hour - Architecture details
+ [Lab 1](cognitive-search-get-start-preview.md) - 2 hours - Create a Cognitive Search Predefined Skill.
+ [Lab 2](cognitive-search-output-field-mapping.md) - 1 hour - Map fields into your Azure Search Index.
+ [Lab 3](cognitive-search-create-custom-skill-example.md) - 2 hours - Create a Cognitive Search Custom Skill.

##Useful Links
+ [Microsoft AI School](https://aischool.microsoft.com/learning-paths)
+ [Microsoft Analytics School](https://learnanalytics.microsoft.com/) 
+ [Microsoft AI Platform](https://www.microsoft.com/en-us/ai)

#Thank you

