#Environment Creation

In this lab we will create an Azure Search Service and a storage account. We recommend to keep both in a new and unique resource group, to make it easier to delete at the end of the workshop, if you want to. We will also upload the data to a blob storage within the storage account.

##Step 1 - Create the Azure Search service

1. Go to the [Azure portal](https://portal.azure.com) and sign in by using your Azure account.

1. Click **Create a resource**, search for Azure Search, and click **Create**. See [Create an Azure Search service in the portal](https://docs.microsoft.com/en-us/azure/search/search-create-service-portal) if you are setting up a search service for the first time.

  ![Dashboard portal](./media/create-service-full-portal.png "Create Azure Search service in the portal")

1. For Resource group, create a resource group to contain all the resources you create in this tutorial. This makes it easier to clean up the resources after you have finished the tutorial.

1. For Location, choose either **South Central US** or **West Europe**. Currently, the preview is available only in these regions.

1. For Pricing tier, you can create a **Free** service to complete tutorials and quickstarts. For deeper investigation using your own data, create a [paid service](https://azure.microsoft.com/pricing/details/search/) such as **Basic** or **Standard**. 

  A Free service is limited to 3 indexes, 16 MB maximum blob size, and 2 minutes of indexing, which is insufficient for exercising the full capabilities of cognitive search. To review limits for different tiers, see [Service Limits](https://docs.microsoft.com/en-us/azure/search/search-limits-quotas-capacity).

  > [!NOTE]
  > Cognitive Search is in public preview. Skillset execution is currently available in all tiers, including free. At a later time, the pricing for this capability will be announced.

1. Pin the service to the dashboard for fast access to service information.

  ![Service definition page in the portal](./media/create-search-service.png "Service definition page in the portal")

1. After the service is created, collect the following information: **URL** from the Overview page, and **api-key** (either primary or secondary) from the Keys page.

  ![Endpoint and key information in the portal](./media/create-search-collect-info.png "Endpoint and key information in the portal")

##Step2 - Create the Azure Blob service and load sample data

The enrichment pipeline pulls from Azure data sources. Source data must originate from a supported data source type of an [Azure Search indexer](https://docs.microsoft.com/en-us/azure/search/search-indexer-overview). For this exercise, we use blob storage to showcase multiple content types.

1. [Download sample data](https://1drv.ms/f/s!As7Oy81M_gVPa-LCb5lC_3hbS-4). Sample data consists of a small file set of different types. 

1. Sign up for Azure Blob storage, create a storage account, log in to Storage Explorer, and create a container named `basicdemo`. See [Azure Storage Explorer Quickstart](https://azure.microsoft.com/en-us/features/storage-explorer) for instructions on all the steps.

1. Using the Azure Storage Explorer, in the `basicdemo` container you created, click **Upload** to upload the sample files. You can also upload the data from the [Azure Portal](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-portal).

1. After sample files are loaded, get the container name and a connection string for your Blob storage. You could do that by navigating to you storage account in the Azure portal. On **Access keys**, and then copy the **Connection String**  field.

  The connection string should be a URL similar to the following hypothetical example:

      ```http
      DefaultEndpointsProtocol=https;AccountName=cogsrchdemostorage;AccountKey=<your key here>==;EndpointSuffix=core.windows.net
      ```

There are other ways to specify the connection string, such as providing a shared access signature. To learn more about data source credentials, see [Indexing Azure Blob Storage](https://docs.microsoft.com/en-us/azure/search/search-howto-indexing-azure-blob-storage).
