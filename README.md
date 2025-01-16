# ScopingRev_Screen
This is a code for screening assistant to a scoping review on mathematical models for the coffee drying process
# Abstract Screening Automation Tool

This repository contains a Python script designed to automate screening abstracts for relevance in research projects. The tool helps identify articles related to mathematical modeling in coffee bean drying, flagging irrelevant entries, and extracting key mathematical approaches mentioned in the abstracts.

## Features
- **Natural Language Processing (NLP):** Uses spaCy for tokenizing abstracts and identifying relevant keywords.
- **Keyword Matching:** Detects predefined keywords for relevance in drying, coffee, and mathematical modeling.
- **Mathematical Approach Extraction:** Employs regex to extract mentions of mathematical and statistical approaches.
- **Clustering:** Uses KMeans clustering to group abstracts based on content similarity.
- **CSV Export:** Saves the screening results, including decisions and comments, to a CSV file.

## Prerequisites
Before running the script, ensure you have the following installed:

- Python 3.7 or higher
- Required Python libraries:
  - pandas
  - spacy
  - scikit-learn
  - openpyxl (for handling Excel files)

Install dependencies with:
```bash
pip install pandas spacy scikit-learn openpyxl
```

Additionally, download the `en_core_web_sm` spaCy language model if not already installed:
```bash
python -m spacy download en_core_web_sm
```

## Input File Requirements
The script processes abstracts stored in an Excel file. The input file must:
- Be in `.xlsx` format
- Contain at least two columns:
  - **Title**: The title of the article
  - **Abstract**: The abstract text

Ensure the file path is correctly specified in the script under the `input_file` variable.

Example input file structure:
| Title                              | Abstract                                                                 |
|------------------------------------|-------------------------------------------------------------------------|
| Optimizing Coffee Drying Models    | This study develops a regression model to optimize coffee bean drying. |
| General Drying Methods             | An overview of general drying methods without mathematical modeling.    |

## Usage
1. download the jupyter note
2. Place your input Excel file in the repository directory and update the `input_file` variable in the script with the file name.
3. Open the script on Jupyter Notebook and run it
4. The results will be saved as `screening_results.csv` in the repository directory. This file contains:
   - **Title**: The article title
   - **Decision**: Yes/No for relevance
   - **Comment**: Explanation for the decision
   - **Mathematical Approach**: Extracted mathematical or statistical approaches
   - **Cluster**: Cluster number assigned by KMeans

## Output File Structure
| Title                              | Decision | Comment                                                          | Mathematical Approach     | Cluster |
|------------------------------------|----------|------------------------------------------------------------------|---------------------------|---------|
| Optimizing Coffee Drying Models    | Yes      | Relevant to drying and mentions moisture or mathematical modeling.| regression, simulation    | 0       |
| General Drying Methods             | No       | Mentions drying but lacks mathematical/statistical modeling.      |                           | 1       |



## Contributions
Contributions are welcome! Feel free to fork the repository and create a pull request if you have suggestions or improvements.

## Contact
For questions or support, please contact idrisssekkak@gmail.com.

