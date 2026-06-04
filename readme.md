📋 Job Listing Automation App
A Python application that automatically scrapes, collects, and stores job listings using the Google Jobs API (via SerpAPI), with SQLite persistence and Excel data integration.

📌 Overview
This project automates the job search process by querying the Google Jobs search engine through SerpAPI, extracting structured job data, and storing it in a normalized SQLite database. It also supports importing supplemental job data from Excel spreadsheets for combined analysis.

✨ Features

Automated Job Scraping — queries Google Jobs for software developer roles in the Boston, MA area across multiple pages using offset-based pagination
Dual Data Sources — ingests job data from both the live SerpAPI feed and Excel spreadsheets (.xlsx)
Normalized SQLite Database — stores data across three relational tables with proper foreign key constraints
Qualification Extraction — parses and stores job qualification highlights from each listing
Error Handling — graceful exception handling on all database insertions to prevent data loss on malformed records
Test Coverage — includes a dedicated tests/ directory and GitHub Actions CI workflow


🗃️ Database Schema
jobs table — core listing data

job title, company name, location, remote status, description, date posted, salary

qualifications table — linked qualification requirements

references job title and company name from jobs

excel_data table — imported spreadsheet records

company name, posting age, job ID, country, location, publications, salary range, salary type, job title


🛠️ Tech Stack
LayerTechnologyLanguagePythonJob Data APISerpAPI (Google Jobs engine)DatabaseSQLite3Excel ParsingopenpyxlCI/CDGitHub ActionsIDEIntelliJ IDEA

🚀 Getting Started
Prerequisites

Python 3.x
A SerpAPI account and API key

Installation
bash# Clone the repository
git clone https://github.com/juovani/Job_Listing_Project.git
cd Job_Listing_Project

# Install dependencies
pip install -r requirements.txt
Configuration
Create a secrets.py file in the root directory with your SerpAPI key:
pythonapi_key = "YOUR_SERPAPI_KEY_HERE"
Run
bashpython main.py
The app will query 5 pages of Google Jobs results (50 listings), store them in your_database.db, and also import any data from Sprint3Data.xlsx.

📁 Project Structure
Job_Listing_Project/
├── main.py               # Main application logic
├── requirements.txt      # Python dependencies
├── Sprint3Data.xlsx      # Sample Excel data source
├── tests/                # Unit tests
├── .github/workflows/    # GitHub Actions CI pipeline
└── .gitignore

👤 Author
Juovani Kirlos

GitHub: @juovani
Email: juovanikirlos@gmail.com
LinkedIn: linkedin.com/in/juovanikirlos


📄 License
This project is open source and available under the MIT License.
