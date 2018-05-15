# Introduction

In this section, we'll set the stage for the rest of the course. We'll start by talking about the motivation behind a cognitive search type of solution and what types of scenarios might call for it. Additionally, we'll give an overview of what Microsoft's Cognitive Search solution is and some of the key concepts you'll need understand before we go forward with the solution and labs.

## Motivation and context

### Azure Search
Developers are constantly looking for PaaS services in Azure (and elsewhere) to achieve better and faster results in the applications they build. While search is a key to many types of applications, search is also a hard and rarely a core expertise area. From an infrastructure standpoint, it needs to have high availability, durability, scale, and operations. From a functionality standpoint, it needs to have ranking, language support, and geospatial capabilities. On top of that, web search engines have set the bar high for search. Users expect: instant results, auto-complete as they type, highlighting hits within the results, great ranking, and the ability to understand what they are looking for, even if they spell it incorrectly or include extra words.

![](media/AzureSearch-Example.png =800x)


The example above illustrates some of the components users are expecting in their search experience. [Azure Search](https://docs.microsoft.com/en-us/azure/search/search-what-is-azure-search) can accomplish these user experience features, along with giving you [monitoring and reporting](https://docs.microsoft.com/en-us/azure/search/search-traffic-analytics), [simple scoring](https://docs.microsoft.com/en-us/rest/api/searchservice/add-scoring-profiles-to-a-search-index), and tools for [prototyping](https://docs.microsoft.com/en-us/azure/search/search-import-data-portal) and [inspection](https://docs.microsoft.com/en-us/azure/search/search-explorer).  

Since you're in this class, you're probably familiar with other search-related solutions like the [Bing Web Search API](https://docs.microsoft.com/azure/cognitive-services/bing-web-search/), [Bing Custom Search](https://docs.microsoft.com/azure/cognitive-services/bing-custom-search/), [SQL Server full text search](https://docs.microsoft.com/sql/relational-databases/search/full-text-search), or even creating dedicated search solutions.. You can see how Azure Search compares to the other solutions [here](https://docs.microsoft.com/en-us/azure/search/search-what-is-azure-search#how-azure-search-compares).

While this is great, there may come a time when you need more than what the [base Azure Search service provides](https://docs.microsoft.com/en-us/azure/search/search-what-is-azure-search#feature-summary): intelligence. 
### Cognitive Search

Cognitive Search adds intelligence to your indexing workloads. Workloads often have unstructured text or non-text content (such as images or scanned document files) - wouldn't it be better if you could still search on them? Cognitive Search is able to extract text-based content, and then cognitive skills can be used to apply entity recognition, language detection, sentiment analysis, OCR (recognize handwriting), and more to your search service. You can also use cognitive skills to analyze images to identify content, famous people or landmarks, and descriptions - and search on that!  

Let's think about a specific example, the assassination of John F. Kennedy by Lee Harvey Oswald. Over the last 40-50 years, there has been significant controversy around the JFK files. Recently, over 50,000 documents were released related to the case. Now, let's say we want to analyze these documents and get to the bottom of what really happened that day in November 1963. It's an unreasonable request (or very time-consuming, depending on your opinion) for us to read all of those documents. With Azure Search, we can search text in some of the documents. But what else might we want to do? And can using Cognitive Search help us?  

1. Maybe we want to be able to extract various entities, perhaps, looking into the occurrences of Oswald in the documents. We don't want to see only the .doc results - we want the images of him, the hand-written notes about him, PDFs and more. Basically, we want to be able to pick out, intelligently, **all** the occurrences of Oswald.  

2. In the case, the investigators used many codenames, or "cryptonyms", which are defined [here](https://www.maryferrell.org/php/cryptdb.php#_GP). We can see that the cryptonym for Oswald was actually "GPFLOOR." So if really want to get **all** occurrences of Oswald, we also need to build into the system that Oswald = GPFLOOR (also that GPIDEAL = JFK, GPLOGIC = LBJ, etc.).

3. Maybe we also want to map how some of the key entities are related. This would take a long time and many lines of code to develop.  

It turns out, that in the documents, you can find that it cost the CIA millions of dollars and a very long time (months) to architect a system (and pay many people to manually tag all the documents) that they could use to try to accomplish the goals above. However, with [Cognitive Search](https://docs.microsoft.com/en-us/azure/search/cognitive-search-concept-intro), two people were able to accomplish the same goals in **two days**.  

How did they do it? First, they stored all the data in Azure blob storage and they extracted the content using Cognitive Search. Next, they were able to simply use [predefined Cognitive Skills](https://docs.microsoft.com/en-us/azure/search/cognitive-search-predefined-skills) ([OCR and handwriting](https://docs.microsoft.com/en-us/azure/search/cognitive-search-skill-ocr), [Computer Vision](https://docs.microsoft.com/en-us/azure/search/cognitive-search-skill-image-analysis), and [Entity extraction](https://docs.microsoft.com/en-us/azure/search/cognitive-search-skill-named-entity-recognition)) to do a lot of analyses that would have otherwise been very complicated and time-consuming to architect and develop. They were also able to create [custom skills](https://docs.microsoft.com/en-us/azure/search/cognitive-search-custom-skill-interface) quickly using [Azure Functions](https://docs.microsoft.com/en-us/azure/search/cognitive-search-create-custom-skill-example) (to address cryptonyms and redactions with Azure ML).  Finally, they created an Azure Search Index on top of it all with a nice web interface so we can explore (you can check it out at jfk-demo.azurewebsites.net/#/).  

As you can probably tell by now, Cognitive Search made the process more efficient and easier to implement. You can watch the full video demo about the JFK files project with Cognitive Search [here](https://developer.microsoft.com/en-us/events/build/content/cognitive-search-ai-powered-content-augmentation).



### Brief Discussion
Can you think of other scenarios where this technology might be useful? We've included a few ideas below:  

- Education  
    - For a student, in a class you may have resources in many different forms: 
        - PowerPoint slides (as .pptx or .pdf)
        - Handwritten notes (scanned on your phone to .pdf, .jpg, or .png)
        - Old tests with answers (.pdf, .jpg, .png, .html)
        - Pictures of whiteboard scribbles from the professor during lectures
        - Etc. 
    - Wouldn't it be nice if you could group them together, perform searches on topics, or create graphs that recognized relationships?
- Manufacturing
    - Even with technology advancements, lots of things are still handwritten in these environments
        - Time sheets
        - Notes during shifts: data about throughput, efficiency, etc.
        - SOPs (standard operating procedures)
    - In addition, there are PDFs (some SOPs), Excel files, Access databases, etc.
    - This could be a good opportunity to coordinate and automate a lot of the analyses
- Justice system
    - Like the JFK files examples, many cases have lots of data in varying forms, similar value could be provided
- Twitter and big events (e.g. festivals like Coachella or NFL games)
    - Could use the service to ingest tweets in near-real time for big events to perform analyses
- And most of all: All enterprises, all industries
    - Every company has unstructured data stored on file servers, cloud devices and local computers: images, pdfs, ppts, xls, docs, html and so on.
    - Most of this huge data volume is soloed and has no metadata, making search a limited experience.
    - Cognitive Search can help any company to enrich the metadata of its own data, any data, helping to increase productivity and even security/compliance.
    - This is the use case we implement in this workshop, what is detailed in the Solution Architecture section.


## Key concepts

Now that you understand the value added by adding Cognitive Search to your solutions, let's dive into what Cognitive Search is and how it works.  

We'll do that by walking through the ["What is Cognitive Search?" documentation](https://docs.microsoft.com/en-us/azure/search/cognitive-search-concept-intro).

Throughout the course, we'll go through implementing a Cognitive Search solution for a specific use case, which we'll cover in the next section.

## Next Step
+ [Solution Architecture](03-Solution-Architecture.md) or [Back to Main Menu](01-readme.md)
