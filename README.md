#Azure Cognitive Search Workshop 

##Welcome
Cognitive Search 
is a new enrichment pipeline that allows you to find rich structured information from documents. This one day training will focus on hands-on activities that develop proficiency on Cognitive Search, an AI-orietend product announced on [Microsoft Build 2018](https://www.microsoft.com/en-us/build). These labs assume an inroductory to intermediate knowledge of [Visual Studio](https://www.visualstudio.com/vs/community/), [Azure Portal](https://portal.azure.com), [Azure Functions](https://azure.microsoft.com/en-us/services/functions/) and [Azure Search](https://azure.microsoft.com/en-us/services/search/). If this is not your case, we have quick start materials in the pre-requisites section of this training.

##Goals
Most challenges observed by customers in these realms are in stitching diverse content together. As such, we placed key concepts and hands-on labs in the context of a broader example.

In this training you will create a cognitive data flow and the enriched information will become part of an Azure Search index. At the end of this workshop, you should be able to:

+ Understand what Cognitive Search is
+ Configure your Cognitive Search service
+ Implement Azure Search features to provide a positive search experience inside applications
+ Configure an Azure Search service to extend your data to enable Cognitive Search
+ Build a solution that enrich, index and search for cognitive data

##Pre-requisites
Since this is an AI training on top of Microsoft Azure Services, there are certain things you need before we start.

1. We will use Visual Studio for some activities. This [link](https://docs.microsoft.com/en-us/visualstudio/ide/visual-studio-ide) has the knwoledge you need to do this workshop. 
2. Together we will create small C# applications. This [short video](https://mva.microsoft.com/en-us/training-courses/c-fundamentals-for-absolute-beginners-16169?l=Lvld4EQIC_2706218949) has the knowledge you need for this training.
3. You need an Microsoft Azure to create the services we use in our solution. You can create a [free account](https://azure.microsoft.com/en-us/free/), use your [MSDN account](https://azure.microsoft.com/en-us/pricing/member-offers/credit-for-visual-studio-subscribers/) or use any other subscription where you have permission to create services.
4. You need a computer with [Visual Studio](https://www.visualstudio.com/downloads/) installed. The Community free edition can be used and it has Windows, MacOS and Linux options. If you don't have permission to install software in your computer, and you don't have Visual Studio installed, you can create a Virtual Machine on Azure.
5. You need a computer with [Bash Command Prompt](https://docs.microsoft.com/en-us/windows/wsl/install-win10) installed. If you are using MacOs or Linux, this step isn't necessary.
6. You may need quick start trainings for [Azure Functions](https://docs.microsoft.com/en-us/azure/azure-functions/) and [Azure Search](https://docs.microsoft.com/en-us/azure/search/)

##Agenda
Since you have finish the pre-requisites, let's start the training. You just need to follow the workshop structure presented below.

+ [Lab 1](cognitive-search-concept-intro.md) - 1 hour - Cognitive Search key concepts. This is a read only introduction.
+ [Lab 2](cognitive-search-get-start-preview.md) - 2 hours - Get Start with Cognitive Search. Here we will create the service, the data source and the Azure Search Index.
+ [Lab 3](cognitive-search-output-field-mapping.md) - 2 hours - Map fields into your Azure Search Index.
+ [Lab 4](cognitive-search-create-custom-skill-example.md) - 2 hours - Create a Cognitive Search Custom Skill.



##Contact us
Thank you for helping us make cognitive search better! We are here to help. The best way to reach the Learn AI Team is through email:

| Alias | Used for |
|-------|----------|
| learnai@microsoft.com | Redelivery, feedback |
| rosouz@microsoft.com | Documentation issues or suggestions |
