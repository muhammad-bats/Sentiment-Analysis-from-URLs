# Sentiment-Analysis-from-URLs

---

This Python script is designed to download a PDF file from a given URL, extract its text, analyze the sentiment of the text using the VADER sentiment analysis tool, and save the results to an Excel file.

## Code Explanation

### 1. Downloading the PDF File

The `get_file` function takes a URL as input, downloads the PDF file from the provided URL, and saves it to the local file system. The user is prompted to enter the desired file name for saving the PDF. If the download is successful, the file is saved with the specified name; otherwise, an error message is displayed.

### 2. Extracting Text from PDF

The `extract_text` function opens the downloaded PDF file and extracts all text from it. The extracted text is returned as a single string, which is later used for sentiment analysis.

### 3. Tokenizing Text into Sentences 

The `tokenize` function uses the NLTK library to split the extracted text into individual sentences. This step is crucial for performing sentence-level sentiment analysis.

### 4. Performing Sentiment Analysis

The `sentiment_analyze` function takes a list of sentences as input and uses the VADER SentimentIntensityAnalyzer to compute sentiment scores for each sentence. The function calculates the average positive, negative, neutral, and compound sentiment scores across all sentences and returns these results.

### 5. Analyzing Sentiment

The `analysis` function calls `sentiment_analyze` to get sentiment scores for the text. It categorizes the overall sentiment as 'POSITIVE', 'NEGATIVE', or 'NEUTRAL' based on the compound score. The results, including sentiment category and scores, are stored in a list (`datalst`) for later use.

### 6. Writing Results to Excel

The `write_excel` function takes the sentiment data and writes it to an Excel file. If the specified Excel file does not exist, it creates a new one. The data is appended to the end of the existing file if it already exists.

### 7. Main Loop

The script runs in a loop, allowing the user to analyze multiple PDF files in succession. After each analysis, the user can choose to continue or stop. The loop keeps track of the total positive sentiment score and calculates the average positivity percentage across all analyzed PDFs.

### 8. Final Output

At the end of the script, the average positivity percentage is printed, providing an overall sentiment score across all the PDFs analyzed during the session.

## How to Use

1. Run the script.
2. Enter the URL of the PDF file you want to analyze.
3. Provide a name for saving the downloaded PDF file.
4. The script will extract the text, perform sentiment analysis, and save the results to an Excel file named `finalexcel.xlsx`.
5. You can choose to analyze another PDF or exit the program.
6. At the end of the session, the script will display the average positivity percentage.

## Example Usage

```
Enter URL: http://example.com/document.pdf
Enter file name you want: myfile.pdf
File downloaded successfully
Text has sentiment: POSITIVE value: 0.8
done
continue? y
...
Average Positivity Percentage is: 75.0%
```

## Notes

- Ensure that the PDF file is text-based, as this script relies on text extraction.
- The Excel file `finalexcel.xlsx` will contain all the sentiment data for the analyzed PDFs.

---
