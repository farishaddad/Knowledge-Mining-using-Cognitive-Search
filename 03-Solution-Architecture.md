# Solution Architecture

In this workshop you will learn how to create a Cognitive Search solution for Enterprise Documents. 

Cognitive Search is an Azure Search feature that lets you use artificial intelligence to extract insights and structured information from business documents like pdf, ppt, docx, xls, html and more. We will create pipelines that use cognitive skills to enrich and bring structure to your data before it gets indexed. 

This solution uses a variety of pre-built cognitive skills and extend the feature by adding a custom skills.

## Use Case

Every company has unstructured data, their business documents, making this solution useful for all your clients. Often, employees have various reasons they may want to search on the unstructured data that accumulates. 
This is a common business scenario which usually has limited search results, because of a lack of metadata as the example you can see in the image below. 

![](media/no-meta.png =400x)

**Cognitive Search uses the most advanced cognitive services, based on Microsoft's AI Platform, to extract and create enriched metadata about your documents, vastly improving the overall search experience.** 

Unless instructed otherwise, in this training you will use a sample dataset that contains documents of different formats (docs, pdfs, images, ppts, etc.) and languages.  



> Note: Since we are working with unstructured data, any set of files can be used. In other words, this could be a **Bring Your Own Data** solution; you can test later with any dataset you want.  
> Some other possible uses for the labs could be:  
>  
>  + Demos: You could keep an environment ready, loaded. 
>  + POCs: You just need to upload some of the client's data and re-execute the enrichment pipeline. **You can prove the concept in front of the client, in minutes**.
>  + Production: Since we are using PaaS, it has SLA and scalability by design.
>  + Personal Use: If you have lots of documents or photos, you can use these labs to analyze them, too.


## Architecture

This simple architecture allows us to focus on the technology and, at the same time, brings flexibility for multiple uses.

![](media/architecture.png)

Please note that:

1. We will provide a sample dataset. This dataset contains documents with multiple languages and formats including HTML, doc, pdf, ppt, png and jpg. They were selected for a better learning experience, showcasing most of the technology capabilities.
2. You can upload the data to blob storage using [Azure Portal](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-portal) or [Azure Storage Explorer](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-storage-explorer), among other options.
3. We will start with a few simple skills and add more complex Cognitive Skills in labs 2 and 3.
4. We will use Azure Search query capabilities to analyze the results.

## Costs
This is a **high level** analysis, to be used only as a reference, based on the [Azure Calculator](https://azure.microsoft.com/en-us/pricing/calculator/) and on the provided dataset. Many other details will change your final price, like region, taxes, discounts, EA and partner fee. The costs will stop being incurred as soon as you delete the services. Another option is to generate templates of everything and create a process to deploy it all on demand, paying for only the minutes that the services existed.

| Item |Cost per day - USD$ | Cost per month - USD$ | Description
|-------|----------|----------|----------|
| Blob Storage | 0.03 | 1.16 |To store the documents |
| Azure Search | 2.42 | 72.72 | To execute all cognitive processing - Basic Tier |
| Azure Functions | 0.20 | 0.20 | To host the custom cognitive service we will create |
| Cognitive Services | 0.00 | 0.00 | To execute the custom cognitive service - Free tier | 
| Total | 2.65 | 74.08 |  | 

That's the order of magnitude of the costs. In addition to all the factors cited above, prices can still be readjusted. Up or down, which has been the most common. For the exact price, look for your reseller or Account manager.

## Interfaces
After initial upload of the files to blob storage,  we will use Fiddler or Postman for [REST API calls](https://docs.microsoft.com/en-us/azure/search/search-fiddler). The image below shows a visual example of Postman being used for Cognitive Search.

![](media/postman.png =1080x)

It is important to notice some details about these tools (Fiddler and Postman):
+ You can save your commands, which is useful for reuse, not only within this workshop, but also in your future projects.
+ You need to create a free account. A confirmation message is emailed to you.
+ You can export all your commands into json format. This file can then be saved into the storage account of the lab, into a cloud storage like OneDrive, or anywhere you like. This process helps you save, share, and reuse your work.
+ These return codes indicate success after an API call request: 200, 201 and 204. 
+ Error messages and warnings are very clear.
+ Besides the API URL and call type, we will use GET/PUT/POST (depending on what action we are taking), and you need to use the header for Content-Type and api-key. The json commands must be placed into the "body / raw" area. If you are struggling using Postman/Fiddler, here's a friendly reminder to [review the resource from the prerequisites](https://docs.microsoft.com/en-us/azure/search/search-fiddler).


## Next step
[Environment Creation](04-Environment-Creation.md) or [Back to Main Menu](01-readme.md)



