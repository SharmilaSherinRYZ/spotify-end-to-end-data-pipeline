#  Musical Insights: Spotify Data Exploration

### Introduction
This project is about collecting music data from Spotify and organizing it for easy analysis. Using AWS, it automatically fetches details like song names, artists, and playlists from Spotify, processes the data to make it useful, and stores it in a structured format. This helps in analyzing trends, popular songs, and other insights efficiently.

### Architecture
<picture>
 <source media="(prefers-color-scheme: dark)" srcset="https://github.com/SharmilaSherinRYZ/spotify-end-to-end-data-pipeline/blob/main/spotify_pipeline_architecture_dgrm.png?raw=true">
 <source media="(prefers-color-scheme: light)" srcset="https://github.com/SharmilaSherinRYZ/spotify-end-to-end-data-pipeline/blob/main/spotify_pipeline_architecture_dgrm.png?raw=true">
 <img alt="YOUR-ALT-TEXT" src="https://github.com/SharmilaSherinRYZ/spotify-end-to-end-data-pipeline/blob/main/spotify_pipeline_architecture_dgrm.png?raw=true">
</picture>

### Dataset/API Used

+ **Spotify API**: Utilized the Spotify Web API [Spotify](https://developer.spotify.com/documentation/web-api) to retrieve data on songs, albums, and artists. The API provides access to detailed metadata and analytics for various music tracks, allowing for comprehensive data analysis and insights.

### Services Used
1.**S3 (Simple Storage Service)**: Amazon S3 is a scalable cloud storage solution by AWS that allows users to store and retrieve data from anywhere on the web, offering high durability, security features, and seamless integration with other AWS services.

2.__AWS lambda__: AWS Lambda is a serverless computing service that allows you to run code without provisioning or managing servers. It automatically scales your applications by executing code in response to events, such as changes in data or HTTP requests, enabling you to build highly scalable and efficient applications with minimal overhead.

3.__Cloud Watch__: Amazon CloudWatch is a monitoring and management service for AWS resources and applications. It provides real-time insights through metrics and logs, enabling you to track performance, set alarms, and automate actions based on defined thresholds, ensuring optimal operation and resource utilization.

4.__Glue Crawler__: AWS Glue Crawler is a tool that automatically discovers and catalogs data in your data stores. It scans your data sources, infers schema and metadata, and creates or updates tables in the AWS Glue Data Catalog, making it easier to query and analyze data using services like Amazon Athena and Redshift.

5.__Data Catalog__: AWS Glue Data Catalog is a central repository that stores metadata about your data sources, making it easy to discover and manage your data. It provides a unified view of data across various services, enabling efficient querying, data discovery, and integration with analytics tools like Amazon Athena and Amazon Redshift.

6.**Athena**: Amazon Athena is a serverless interactive query service that allows you to analyze data stored in Amazon S3 using standard SQL. It enables quick and easy querying without the need for data loading or infrastructure management, making it ideal for data analysis and reporting.

### Installed Packages

- **Spotipy**: A library for accessing the Spotify Web API.
- **Boto3**: The AWS SDK for Python, for interacting with AWS services.
- **Pandas**: A data manipulation and analysis library for Python.
  
#### Installation

To install the required packages, run:

```
pip install spotipy
pip install boto3
pip install pandas
```
### Project Execution Flow

Extract Data from API -> Lambda trigger every(1 hour) -> Run extract code -> Store raw data -> Trigger Transfom Function -> Transform Data and Load it -> Query using Athena
