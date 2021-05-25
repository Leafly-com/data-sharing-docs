# Leafly Strain Data API

Provides access to Leafly strain data. Data is made available via CSVs. Each CSV represents a data source whose content is curated for each subscription tier.

**Note:** Your subscription tier will be determined by the API; it is *not* a parameter you include in your request.

**Table of Contents**

- [Prerequisites](#prerequisites)
- [Data Sources](#data-sources)
- [Usage](#usage)
- [Troubleshooting](#troubleshooting)

## Prerequisites
- API key (provided by account manager)

## Data Sources

| Data Source | Endpoint |
| --- | --- |
| Attributes | `...leafly.com/api/v1/strains/attributes` |
| Info | `...leafly.com/api/v1/strains/info`|
| Reviews | `...leafly.com/api/v1/strains/reviews` |

See [here](DATA_SOURCE_SCHEMAS.md "Data source schemas") for the schema of each data source.

## Usage

1. Send a GET request. Include your API key in your request headers using the key `HTTP_X_LEAFLY_API_KEY`.

**Python 3.x**

```python
import requests

my_api_key = '420'
# let's get the strain attributes export
url = '...leafly.com/api/v1/strains/attributes'
headers = {'HTTP_X_LEAFLY_API_KEY': my_api_key}

response = requests.get(url, headers=headers)
print(response.json())
```

2. Response will be in JSON format and will contain the following keys:

  - `last_modified`: UTC timestamp indicating when the CSV was generated
  - `download_url`: a [presigned URL](https://docs.aws.amazon.com/AmazonS3/latest/userguide/ShareObjectPreSignedURL.html "AWS presigned URL doc") that will enable you to download the CSV

```json
{
  "last_modified": "2021-05-24T08:03:17.169Z",
  "download_url": "https://data-warehouse-data.s3.us-west-2.amazonaws.com/strain_data_api_exports/tier%3Dstandard/strain_reviews.csv.gz?response-content-disposition=attachment%3B%20filename%3D%22strain_reviews.csv.gz%22&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIA5G7KJKOGGAZMKU4H%2F20210525%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210525T025749Z&X-Amz-Expires=900&X-Amz-SignedHeaders=host&X-Amz-Signature=c86c1d1beab998aa5e2c35ec33357fca05cb81e9fa3975e0b16df219cef84c8d"
}
```

**Note:** The download URL is valid for 15 minutes.

3. Use the value of `download_url` in a GET request to retrieve the CSV content or paste it into a browser and search, which will download the CSV file to your computer.

**Note:** The CSV will be GZIP compressed.

## Troubleshooting

- Authentication Error
