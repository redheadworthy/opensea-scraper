> [!TIP] 
> # How to run
> 
> ## Install Python
> 
> 1. Go to the official Python website: https://www.python.org/downloads/release/python-3139/
> 2. Scroll down to the files part. Then download the Windows installer (64-bit)
> 3. Once downloaded, run the installer.
> 4. ✅ Important: On the first screen of the installer, check the box that says
> “Add Python to PATH” before clicking Install Now.
> ## How to download the repo
> Click the button below to download the code as a .zip:
>
> <a href="https://github.com/redheadworthy/opensea-scraper/archive/refs/heads/main.zip"><img src="https://img.shields.io/badge/⬇️_Download_ZIP-2ea44f?style=for-the-badge&logo=github&logoColor=white" alt="Download ZIP"></a>
>
> 
> Now extract the .zip folder
> 
> ## Run the script
> 
> Open the command prompt inside the extracted folder and run:
>
> `py opensea_scraper.py`
> 
>  or
> 
> `python opensea_scraper.py`


# OpenSea Metadata Scraper

## Overview

The **OpenSea Metadata Scraper** is a Python tool that collects metadata information for NFTs from OpenSea using their API. It fetches key details such as the NFT’s name, description, image URL, owner, sale price, currency, and attributes, then saves the data in a structured CSV file.

### Features

- **Automated Metadata Retrieval**: Fetches data for NFTs in a collection by contract address and token ID.
- **Attribute Flattening**: Organizes each trait and characteristic of the NFT into columns.
- **CSV Output**: Saves the results to a CSV file for easy filtering, sorting, and analysis.

### Prerequisites

To use this script, you’ll need:

1. Python 3.x
2. Required libraries: `requests` and `pandas`

Install the necessary libraries with:

```bash
pip install requests pandas
```

### Usage

#### Step 1: Update the Contract Address and Token IDs

Replace `contract_address` with the actual contract address of the NFT collection on OpenSea, and populate `token_ids` with the IDs of the NFTs whose metadata you want to scrape.

#### Step 2: Run the Script

Run the script using the following command:

```bash
py opensea_scraper.py
```

The script will fetch metadata for each NFT specified in `token_ids`, extract relevant information, and save it to a CSV file named `opensea_metadata.csv`.

### Example

If your contract address is `0x12345...` and the token IDs are `[1, 2, 3]`, modify the script as follows:

```python
contract_address = "0x12345..."
token_ids = [1, 2, 3]
```

Then run:

```bash
py opensea_scraper.py
```

### Data Output

The CSV file will include columns such as:

- **Name**: NFT name
- **Description**: Description of the NFT
- **Image URL**: URL to the NFT image
- **Owner**: Username of the current owner
- **Sale Price**: Most recent sale price, if available
- **Sale Currency**: Currency symbol for the sale price
- **Attributes**: Each trait (e.g., "Background", "Rarity") appears in its own column with respective values

### Important Notes

- **API Rate Limiting**: OpenSea enforces rate limits on their API. A short delay between requests (`time.sleep(1)`) is used to avoid hitting these limits.
- **Variable Metadata**: NFT metadata structures may vary between collections. You may need to adjust `extract_metadata` to fit your collection’s metadata fields.

### Limitations

- **Platform-Specific**: This script is designed specifically for OpenSea. Adjustments may be needed to scrape metadata from other platforms.
- **API Access**: Be mindful of API rate limits and consider using an API key if OpenSea starts enforcing stricter rate limits.

### Future Enhancements

- **Error Handling**: Improve handling for cases where the API fails to return data for certain token IDs.
- **Database Storage**: Store data in a database for better long-term analysis and retrieval.
- **Automated Scheduling**: Add scheduling for regular updates to the metadata for dynamic NFT collections.

--- 

This script provides a starting point for scraping metadata from OpenSea. Let me know if you need help with specific adjustments, like handling custom attributes or using additional API features!
eay