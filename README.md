# PDF Table Extractor & Analyzer
This project contains a Python script designed to automatically extract tables from a PDF file, consolidate them into a single CSV file, and perform basic statistical analysis on specific columns of the extracted data.

It leverages the tabula-py library for robust table extraction and pandas for efficient data manipulation and analysis.

## 📋 Features
Robust Table Extraction: Intelligently tries two different extraction methods (lattice for grid-lined tables and stream for tables without lines) to maximize the chance of success.

Multi-Page Support: Scans all pages of the PDF for tables using the pages="all" setting.

Data Consolidation: Combines all extracted tables from every page into a single, clean pandas DataFrame.

CSV Output: Saves the final combined table to a CSV file named final_output.csv.

Basic Data Analysis: After extraction, it automatically reads the CSV to:

Create a new summary column (Total Marks).

Calculate the mean and standard deviation of the new column.

## ⚙️ Prerequisites
Before you run the script, you need to have the following installed:

Python 3.x

Java: The tabula-py library is a wrapper for the original Tabula Java program. You must have Java installed on your system and available in your system's PATH.

Python Libraries: The script depends on tabula-py and pandas.

## 🚀 Installation
Clone this repository to your local machine:

### Bash
git clone <your-repository-url>
cd <your-repository-name>
Install the required Python libraries using pip:

### Bash
pip install tabula-py pandas

## ▶️ How to Use
Place Your PDF: Put the PDF file you want to process into the same directory as the script. Rename your file to Tabled Pdf.pdf or change the pdf_file variable inside the script to match your PDF's filename.
Run the Script: Execute the Python script from your terminal.

### Bash
python your_script_name.py
Get the Output: The script will:
Print status messages to the console, including the mean and standard deviation.

Generate a final_output.csv file in the same directory containing all the combined table data.

## 🔧 Customization
This script is set up for a specific PDF structure. To adapt it for your own use, you will likely need to change the data analysis section.

Open the script and find these lines:
Python

#### \ ... (extraction part) ... /

df = pd.read_csv("final_output.csv", skiprows=1)
df.head()

# MODIFY THESE COLUMN NAMES to match your CSV file
df["Total Marks"] = df["Internal Test-1\rfreezed"] + df["Unnamed: 3"]
print(df)

mean_total = df["Total Marks"].mean()
print("Mean of Total Marks:", mean_total)
#### \ ... /
skiprows=1: This skips the first row of the CSV. You may need to remove or adjust this depending on your PDF's table headers.

df["Internal Test-1\rfreezed"] + df["Unnamed: 3"]: Change these column names to match the actual headers in your generated final_output.csv file. You can open the CSV in a spreadsheet program to easily see the correct column names.
