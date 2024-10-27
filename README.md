# Sentiment Analysis Project

## Overview

This project performs text analysis on articles extracted from provided URLs(through APIs). It retrieves the article's title and content, cleans and processes the text, and calculates various analytical metrics to provide insights into the writing style, sentiments and readability of the content.

## Technologies Used

- Python
- Libraries:
  - `requests`: For making HTTP requests to fetch articles.
  - `BeautifulSoup` (from `bs4`): For parsing HTML content.
  - `pandas`: For data manipulation and analysis.
  - `nltk`: For natural language processing tasks.
  - `textblob`: For sentiment analysis.
  - `openpyxl`: For handling Excel file operations.
  - `html5lib`: For parsing HTML documents.

## Installation

1. Clone the repository:


2. Install the required packages:

   ```bash
   pip install requests openpyxl html5lib bs4 pandas nltk textblob
   ```

3. Download NLTK data:

   Ensure you have the necessary NLTK resources by running the following in a Python shell:

   ```python
   import nltk
   nltk.download('punkt')
   nltk.download('punkt_tab')
   nltk.download('cmudict')
   ```

## Project Structure

```
.
├── Input.xlsx                 # Excel file containing the list of URLs for articles.
├── StopWords                  # Directory containing stop words text files.
│   ├── StopWords_Auditor.txt
│   ├── StopWords_Names.txt
│   ├── StopWords_DatesandNumbers.txt
│   ├── StopWords_Currencies.txt
│   ├── StopWords_Generic.txt
│   ├── StopWords_GenericLong.txt
│   └── StopWords_Geographic.txt
├── MasterDictionary           # Directory containing sentiment dictionaries.
│   ├── positive-words.txt
│   └── negative-words.txt
├── extracted_txt_folder       # Folder where extracted articles are saved.
├── crawler.log                # Log file for tracking errors and process flow.
├── Output Data Structure.xlsx  # Excel file with the analysis results.
└── README.md                  # Project documentation.
```

## Usage

1. Prepare your input Excel file (`Input.xlsx`) with a column named `URL_ID` and another named `URL` containing the URLs of the articles you want to analyze.
2. Place your stop words and sentiment dictionaries in the appropriate directories.
3. Run the script:
4. The results will be saved in `Output Data Structure.xlsx`, and individual articles will be saved in the `extracted_txt_folder`.

## Analysis Metrics

The following metrics are calculated for each article:

- **Positive Score**: Number of positive words.
- **Negative Score**: Number of negative words.
- **Polarity Score**: A measure of sentiment expressed in the text.
- **Subjectivity Score**: A measure of the subjectivity of the text.
- **Avg Sentence Length**: Average number of words per sentence.
- **Percentage of Complex Words**: Percentage of words with three or more syllables.
- **Fog Index**: Readability score based on sentence length and complex words.
- **Avg Words per Sentence**: Average number of words per sentence.
- **Complex Word Count**: Count of words with three or more syllables.
- **Word Count**: Total number of words.
- **Syllable per Word**: Average number of syllables per word.
- **Personal Pronouns**: Count of personal pronouns.
- **Avg Word Length**: Average length of words in the text.

## Logging

The script logs the process in `crawler.log`, which records successful and failed attempts to retrieve articles.


## Acknowledgments

- NLTK and TextBlob for their powerful NLP capabilities.
- Beautiful Soup for its ease of use in web scraping.
