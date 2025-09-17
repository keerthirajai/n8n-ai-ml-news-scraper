# n8n-ai-ml-news-scraper
This n8n workflow scrapes AI/ML news from an RSS feed, analyzes titles for keywords like 'AI', 'LLM', and 'deep learning', 'generative ai', and filters for relevant articles. It then appends the filtered data, along with a summary of keyword frequencies, to a Google Sheet. It's a quick and easy way to stay on top of industry trends


# AI/ML News Scraper & Analyzer

This project is an **n8n workflow** designed to automatically **scrape** the latest news related to **Artificial Intelligence** and **Machine Learning**, analyze the content for specific **keywords**, and log the results into a **Google Sheet**.

The **workflow** fetches articles from the KDnuggets **RSS feed**, filters for relevant topics, and provides a summary of keyword frequencies.

## Features

* **Automated Scraping:** Fetches news from a specified **RSS feed**.
* **Keyword Analysis:** Identifies articles containing terms like '**AI**', '**machine learning**', '**neural**', '**deep learning**', '**LLM**', and '**generative**'.
* **Data Organization:** Stores the scraped and analyzed data in a structured **Google Sheet**.
* **Summary Report:** Includes a summary row with **keyword** counts for a quick overview.
* **Cleanliness:** Clears the sheet before each run to ensure the data is always up-to-date.

***

## Prerequisites

* **n8n:** This project requires a running instance of [n8n](https://n8n.io/). You can use the desktop app, a self-hosted instance (docker), or the cloud version.
* **Google Account:** A Google account with access to **Google Sheets** is needed to store the data.

## Setup Instructions

### 1. Import the Workflow

1.  Open your **n8n** instance.
2.  Go to the **Workflows** section.
3.  Click **Import from URL** or **Import from File**.
4.  If importing from file, use the `Data_Scraping_Tool_AI_ML_news.json` file provided in this repository.

### 2. Configure Credentials

1.  In **n8n**, navigate to **Credentials**.
2.  Add a new credential of type **Google Sheets** OAuth2 API.
3.  Follow the instructions to connect your Google Account and grant **n8n** access to your **Google Sheets**. Name the credential appropriately (e.g., "Google Sheets").

### 3. Update Google Sheet Details

1.  Create a new **Google Sheet** where you want the data to be stored.
2.  Note the **Document ID** from the URL. (e.g., `https://docs.google.com/spreadsheets/d/YOUR_DOCUMENT_ID_HERE/edit`).
3.  Open the `Clear sheet` and `Append row in sheet` nodes in the **workflow**.
4.  In the `documentId` field, replace the placeholder value with your **Google Sheet**'s ID.
5.  In the `sheetName` field, enter the name of your worksheet (e.g., `Data Scrapper AI/ML`).
6.  Ensure the credentials field is set to the **Google Sheets** credential you created in the previous step.

### 4. Run the Workflow

1.  After completing the setup, click the **Execute Workflow** button in the **n8n** editor.
2.  The **workflow** will run, scrape the news, and populate your **Google Sheet** with the results.

## Workflow Visualization

## Contributing

Feel free to open issues or submit pull requests to improve this **workflow**.

***

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
