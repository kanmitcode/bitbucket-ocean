# Bitbucket-Ocean Integration

## Overview

The **Bitbucket-Ocean Integration** enables seamless synchronization between Bitbucket and Port's Ocean framework. It allows users to ingest Bitbucket projects, repositories, and pull requests into Port, providing a unified view of their development workflows.

## Description

This integration provides automated data synchronization between Bitbucket and Ocean. It fetches repositories, projects, and pull requests from Bitbucket and ingests them into Port, enabling streamlined visibility and management within the Ocean framework.

## Prerequisites

Before setting up the integration, ensure you have the following:

* **Port Account**: Access to your Port workspace.
* **Bitbucket Account**: Administrative access to your Bitbucket workspace.
* **Ocean CLI**: Installed on your local machine. Follow the [Ocean CLI installation guide](https://ocean.getport.io/getting-started/) if not installed.

## Installation

### 1\. Clone the Repository

``` bash
git clone https://github.com/kanmitcode/bitbucket-ocean.git
cd bitbucket-ocean
```

### 2\. Set Up Environment Variables

Create a `.env` file in the root directory and add the following:

``` ini
BITBUCKET_WORKSPACE=<your-bitbucket-workspace>
BITBUCKET_USERNAME=<your-bitbucket-username>
BITBUCKET_APP_PASSWORD=<your-bitbucket-app-password>
BITBUCKET_ACCESS_TOKEN=<your-bitbucket-app-password>
PORT_API_KEY=<your-port-api-key>
```

### 3\. Install Dependencies

``` bash
pip install -r requirements.txt
```

## Running the Integration

### Fetch and Ingest Data

``` bash
export PYTHONPATH=$(pwd)
python3 -m bitbucket_ocean.main
```

This fetches projects, repositories, and pull requests from Bitbucket and pushes them to Port.

### Running Test

If you want to run:

``` bash
pytest tests/
```

## API Endpoints

### Fetch Bitbucket Projects

``` http
GET https://api.bitbucket.org/2.0/workspaces/{workspace}/projects
```

### Fetch Bitbucket Repositories

``` http
GET https://api.bitbucket.org/2.0/repositories/{workspace}
```

### Fetch Pull Requests

``` http
GET https://api.bitbucket.org/2.0/repositories/{workspace}/{repo_slug}/pullrequests
```

## Logging and Debugging

Logging is configured at the `DEBUG` level. If needed, modify the logging settings in `bitbucket_ocean_integration.py`:

``` python
logging.basicConfig(level=logging.INFO, format="%(asctime)s - %(levelname)s - %(message)s")
```

## Added Docs Pages

* Bitbucket-Ocean Integration (`/build-your-software-catalog/sync-data-to-catalog/git/bitbucket-ocean`)


## PRs

Integration code
https://github.com/port-labs/ocean/pull/1407 

Documentation
https://github.com/port-labs/port-docs/pull/2046

Port Organization ID
org_afzQpUGuZsfqGqcS

## Conclusion

The Bitbucket-Ocean integration streamlines your development workflow by syncing Bitbucket data into Port. Follow the installation steps to get started and customize it as needed for your organization.
