#Lab 2 - Challenge!

In this lab we will verify the lack of images processing results we got from the previous lab and fix it adding image analysis skill sets to our pipeline.


##The Problem
There were png and jpg images within the provided dataset. If you decided to bring your own data, it was suggested to also include images. But we did not add any pre defined skillset for image analysis. This is exactly what we will do now, but first of all let's check the problem with steps 1 and 2


###Step 1
Let's check the indexer status again, it has valuable information about our "images problem". It is the same command we used in the previos lab, pasted below again. If you used another indexer name, just change it in the URL.

```http
GET https://[servicename].search.windows.net/indexers/demoindexer/status?api-version=2017-11-11-Preview
api-key: [api-key]
Content-Type: application/json
```
If you look for the results of the image files, you will see that nothing was extracted. 

###Step 2
Now let's again repeat a previous lab request, but with another analysis. We will re-execute the verify content step but querying all fields. If you used another index name, just change it in the URL.

```http
GET https://[servicename].search.windows.net/indexes/demoindex/docs?search=*&$select=*&api-version=2017-11-11-Preview
api-key: [api-key]
Content-Type: application/json
```
You will problably see something similar to the image below, no information for the images we have. 

![](media/no-images-info.png =800x)


##How we will fix it?

We will fix it, but there is a challenge for you increase your learning about Predefined Skills. The next steps will guide you trough the challenge and don't worry if you get stuck, we will share the solution too. 

###Step 3
Two of the nine [predefined skills](https://docs.microsoft.com/en-us/azure/search/cognitive-search-predefined-skills) are related to image analysis. Your first assignment is to read about how to use them using this [link](https://docs.microsoft.com/en-us/azure/search/cognitive-search-concept-image-scenarios). 

As the example of this link, we will add both skills to our skillset, to create a solution really usefull for any kind of data.

###Step 4
We need to prepare the environment to add the image analysis we will create. The most practical approach is to delete the objects from Azure Search and rebuild them. Resource names are unique, deleting an object lets you recreate it using the same name. You can use Azure Portal do delete the index and the indexer.

Skillsets can only be deleted through an HTTP command, let's use another API call request to delete it. If you used another skillset name, just change it in the URL.

```http
DELETE https://[servicename].search.windows.net/skillsets/demoskillset?api-version=2017-11-11-Preview
api-key: [api-key]
Content-Type: application/json
```

###Step 5




 


















The image analysis skill extracts a rich set of visual features based on the image content. For instance, you can generate a caption from an image, generate tags, or identify celebrities and landmarks.

## @odata.type  
Microsoft.Skills.Vision.ImageAnalysisSkill 

## Skill Parameters

Parameters are case-sensitive.

| Parameter name	 | Description |
|--------------------|-------------|
| defaultLanguageCode	|  A string indicating which language to return. The service returns recognition results in a specified language. If this parameter is not specified, the default value is "en". <br/><br/>Supported languages: <br/>*en* - English, Default <br/> *zh* - Simplified Chinese|
|visualFeatures |	An array of strings indicating what visual feature types to return.  <br/><br/> Valid visual feature types include:<br/> 	*Categories* - categorizes image content according to a taxonomy defined in the Cognitive Services [documentation](https://docs.microsoft.com/azure/cognitive-services/computer-vision/category-taxonomy). <br/> *Tags* - tags the image with a detailed list of words related to the image content. <br/>	*Description* - describes the image content with a complete English sentence. <br/>	*Faces* - detects if faces are present. If present, generate coordinates, gender and age.<br/>	*ImageType* - detects if image is clipart or a line drawing.<br/>	*Color* - determines the accent color, dominant color, and whether an image is black&white. <br/>*Adult* - detects if the image is pornographic in nature (depicts nudity or a sex act). Sexually suggestive content is also detected.|
| details	| An array of strings indicating which domain-specific details to return.  <br/><br/> Valid visual feature types include: <br/> *Celebrities* - identifies celebrities if detected in the image. <br/> *Landmarks* - identifies landmarks if detected in the image.
 |

## Skill Inputs

| Inputs	 | Description |
|--------------------|-------------|
| url | Unique locator for the image. It could be a web url or the location of blob storage.|



##	Sample definition

```json
 {
    "@odata.type": "#Microsoft.Skills.Vision.ImageAnalysisSkill",
    "visualFeatures": ["tags","faces"],
    "defaultLanguageCode": "en",
    "inputs": [
      {
        "name": "url",
        "source": "/document/metadata_storage_path"
      }
    ],
    "outputs": [
      {
        "name": "categories",
        "targetName": "myCategories"
      },
      {
        "name": "tags",
        "targetName": "myTags"
      },
      {
        "name": "description",
        "targetName": "myDescription"
      },
      {
        "name": "faces",
        "targetName": "myFaces"
      },
      {
        "name": "imageType",
        "targetName": "myImageType"
      },
      {
        "name": "color",
        "targetName": "myColor"
      },
      {
        "name": "adult",
        "targetName": "myAdultCategory"
      }
    ]
  }
```

##	Sample Input

```json
{
    "values": [
      {
        "recordId": "1",
        "data":
           {
             "url": "https://storagesample.blob.core.windows.net/sample-container/image.jpg"
           }
      }
    ]
```


##	Sample Output

```json
{
    "values": [
      {
        "recordId": "1",
        "data":
           {
            "categories": [{
                "name": "people_",
                "score": 0.984375,
                "detail": {
                  "celebrities": [{
                    "faceRectangle": {
                      "top": 200,
                      "left": 293,
                      "width": 149,
                      "height": 149
                    },
                    "name": "Michael Jackson",
                    "confidence": 0.96337
                  }]
                }
              }]
           }
      }
    ]
}
```


## Error cases
In the following error cases, no elements are extracted.

| Error Code | Description |
|-------|-------------|
| NotSupportedLanguage | The language provided is not supported. |
| InvalidImageUrl | Image URL is badly formatted or not accessible.|
| InvalidImageFormat | Input data is not a valid image. |
| InvalidImageSize | Input image is too large. |
| NotSupportedVisualFeature  | Specified feature type is not valid. |
| NotSupportedImage | Unsupported image, e.g. child pornography. |
| InvalidDetails | Unsupported domain-specific model. |

## See also

+ [Predefined skills](cognitive-search-predefined-skills.md)
+ [How to define a skillset](cognitive-search-defining-skillset.md)