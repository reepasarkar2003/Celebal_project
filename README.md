
## Pipelines

### FetchCountryDataPipeline
- Fetches data for five countries (India, US, UK, China, Russia) from a REST API.
- Saves the data as JSON files in Azure Blob Storage.

### CustomerDataPipeline
- Copies customer data from SQL Database to Azure Data Lake Storage if the record count is more than 500.
- Calls the ProductDataPipeline if the customer record count is more than 600.

### ProductDataPipeline
- Copies product data from SQL Database to Azure Data Lake Storage based on customer count passed as a parameter.

## Linked Services

- `RestService`: Connection to the REST API.
- `SqlDbService`: Connection to the SQL Database.
- `BlobStorageService`: Connection to Azure Blob Storage.

## Datasets

- `CountryDataDataset`: Dataset for country data fetched from the REST API.
- `CustomerDataDataset`: Dataset for customer data in the SQL Database.
- `ProductDataDataset`: Dataset for product data in the SQL Database.

## Triggers

- `TwiceDailyTrigger`: Trigger to run the FetchCountryDataPipeline twice daily at 12:00 AM and 12:00 PM IST.
