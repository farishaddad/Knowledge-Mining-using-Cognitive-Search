#Solution Architecture

In this workshop we will create a simple Cognitieve Search solution to ingest, extract, index and search cognitive skills for any kind of enterprise documents: Microsoft Office, images, pdfs and much more.


##Use Cases

Every company has this kind of unstructured data, making this solution usefull for all your clients. Since we are working with unstructured data, any file can be used. A common scenario has limited searching results because on lack of metadata and inexistence of AI processing to analyze the content. Cognitive Search uses the most advanced cognitive services, based no Microsoft AI Platform, to extract and create enriched metadadata about your documents, improving the search experiences. 

Possible uses for this solution are:

+ Demos: You leave an environment ready, loaded. 
+ POCs: You just need to upload some client's data. **You can proove the concept in front of the client, in minutes**.
+ Production: Since we are using PaaS, it has SLA and scallabilitty by design.
+ Personal Use: If you have lots of documents or photos, you can use it too.

##Architecture

This simple architecture allows us to focus on the technology and at the same time brings flexibilty for multiple uses.

![](media/architecture.png)

Please notice that:

1. We will provide a data sample but you can use your own (BYOD - Bring your own data). **If BYOD is your case, we suggest you to use documents with multiple languages and formats including HTML, doc, pdf, ppt, png and jpg. If your documents mention public companies and figures, the workshop experience will be better. But we are handling unstructured data, any files will be processed. This recomendations are suggestions for a better learing experience**.
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

##Interfaces
After initial upload of the files to blob storage, what is done within the first lab, we will use Fiddle or Postman for [REST API calls](https://docs.microsoft.com/en-us/azure/search/search-fiddler). The image below has some visual examples of POSTMAN been used for Cognitive Search.

![](media/postman.png =1080x)

It is important to noitice some details about these tools:
+ You can save your commands, what is usefull for re-use not only within this workshop but also in the future.
+ You need to create a free account. A confirmation message is sent to your email.
+ You can export all your commands into json format. This file can be saved into the storage account of the lab, into a cloud storage like OneDrive or anywhere you like. This process help you to save, share and re-use your work.
+ These return codes indicates success after an API call request: 200, 201 and 204. 
+ Error messages and warnings are very clear.
+ Besides the API URL and call type, we will use GET/PUT/POST, you need to use the header for Content-Type and api-key. The json commands must be placed into the "body / raw" area. 






## Next step
[Environment Creation](04-Environment-Creation.md) or [Back to Main Menu](01-readme.md)



