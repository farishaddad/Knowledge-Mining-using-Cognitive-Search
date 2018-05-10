#	Solution Architecture

In this workshop we will create a simple Cognitieve Search solution to ingest, extract, index and search cognitive skills for any kind of enterprise documents: Microsoft Office, images, pdfs and much more.


##Use Cases

Every company has this kind of unstructured data, making this solution usefull for all your clients. A common scenario has limited searching results because on lack of metadata and inexistence of AI processing to analyze the content. Cognitive Search uses the most advanced cognitive services, based no Microsoft AI Platform, to extract and create enriched metadadata about your documents, improving the search experiences. 

Possible uses for this solution are:

+ Demos: You leave an environment ready, loaded.
+ POCs: You just need to upload some client's data.
+ Production: Since we are using PaaS, it has SLA and scallabilitty by design.
+ Personal Use: If you have lots of documents or photos, you can use it too.

##Architecture

This simple architecture allows us to focus on the technology and at the same time brings flexibilty for multiple uses.

![](media/architecture.png)

Please notice that:

1. We will provide a data sample but you can use your own.
2. You can upload the data to blob storage using [Azure Portal](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-portal) or [Azure Storage Explorer](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-storage-explorer), among other options.
3. We will start simple and add more complex Cognitive Skills in labs 2 and 3.
4. We will use Azure Search query capabilities to analyze the results.

##Costs
This is a high level analysis, to be used only as a reference, based on the [Azure Calculator](https://azure.microsoft.com/en-us/pricing/calculator/) and on the provided dataset. There are many details that will change your final price like region, taxes, discounts, EA and partner fee. The costs will stop to be billed as soon as you delete the services. Another option you have is to generate templates of everything and create a process to deploy it all on demand, paying just the minutes the services existed.

| Item |Cost per day - USD$ | Cost per month - USD$ | Description
|-------|----------|----------|----------|
| Blob Storage | 0.03 | 1.16 |To store the documents |
| Azure Search | 2.42 | 72.72 | To execute all cognitive processing - Basic Tier |
| Azure Functions | 0.20 | 0.20 | To host the custom cognitive service we will create |
| Cognitive Services | 0.00 | 0.00 | To execute the custom cognitive service - Free tier | 
| Total | 2.65 | 74.08 |  | 

That's the order of magnitude of the costs. In addition to all the factors cited above, prices can still be readjusted. Up or down, which has been the most common. For the exact price, look for your reseller or Account manager.



## Next step

+ [Lab 1](Lab-1.md)



