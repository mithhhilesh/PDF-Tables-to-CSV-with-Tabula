# Tabula PDF Data Extraction 📊

Extract tables from PDF files easily using Tabula and Python!

## What is Tabula?

Tabula helps you extract data from PDF tables and convert them to CSV, Excel, or work with them in Python. No more copy-pasting data manually!

## Quick Setup ⚡

### Step 1: Install Java ☕
Tabula needs Java to work.

1. Check if you have Java: Open terminal/command prompt and type:
   ```bash
   java -version
   ```
2. If you don't see a version number, download Java from [Adoptium](https://adoptium.net/) (get version 11 or 17)

### Step 2: Install Tabula

**For Python users:**
```bash
pip install tabula-py
```

**For GUI users:**
1. Go to [Tabula releases](https://github.com/tabulapdf/tabula/releases)
2. Download the file for your OS (Windows/Mac/Linux)
3. Unzip and run the application

## Basic Usage 🚀

### Extract Your First Table

```python
import tabula

# Extract all tables from a PDF
tables = tabula.read_pdf("your_file.pdf")

# Save the first table as CSV
tables[0].to_csv("my_table.csv", index=False)

print("Done! Check your CSV file.")
```

### More Examples

```python
# Extract from specific pages
tables = tabula.read_pdf("file.pdf", pages="1-3")

# Save directly as CSV
tabula.convert_into("file.pdf", "output.csv", output_format="csv")

# Extract all pages
all_tables = tabula.read_pdf("file.pdf", pages="all")
```

## Using the GUI 🖱️

1. Open Tabula application (Jupyter Notebook File)
2. Click "Browse" and select your PDF
3. Click on the table you want to extract
4. Hit "Preview & Export"
5. Download as CSV!

## Common Issues & Fixes 🔧

**"Java not found" error:**
- Make sure Java is installed and restart your terminal

**Empty results:**
- Try: `tabula.read_pdf("file.pdf", lattice=True)`
- Or: `tabula.read_pdf("file.pdf", stream=True)`

**Table looks messy:**
- The PDF might have a complex layout
- Try different extraction methods shown above

## Need Help? 🆘

- **Tabula Tutorial**: [https://tabula.technology/](https://tabula.technology/)
- **Python Examples**: [tabula-py GitHub](https://github.com/chezou/tabula-py)
- **Beginner Guide**: [Dataquest Tutorial](https://www.dataquest.io/blog/python-tutorial-web-scraping-pdfs-tabula/)

## Requirements 📋

Create a `requirements.txt` file:
```
tabula-py
pandas
```

Install with: `pip install -r requirements.txt`

---

~ this was generated with use of Claude for reference purpose
