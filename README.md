# Job Applicant Verification 


## Project Overview

This project compares the differences in candidate-to-position matchings using verified and unverified data. Verified data consist of curated, accurate representations of applicant skills and experiences, while unverified data are raw resume data. By analyzing the differences in matches using unverified and verified candidate data, this project aims to explore the role of data quality in job applicant matching systems.

## Datasets

### Verified Dataset

Not provided in this repository; users must supply their own verified dataset with the following fields:
 Age, Accessibility, EdLevel, Employment, Gender, MentalHealth, MainBranch, YearsCode, YearsCodePro, Country, PreviousSalary, HaveWorkedWith, ComputerSkills, Employed
 
 Example row:
 19341, <35, No, Undergraduate, 1, Man, No, Dev, 4, 0, Brazil, 4944, Python;SQL;Docker;Git, 40, 1


### Unverified Dataset: stackoverflow_full.csv

Example row:
 0, <35, No, Master, 1, Man, No, Dev, 7, 4, Sweden, 51552.0, Python;PostgreSQL, 4, 0


### GetOnBoard Jobs Dataset: GetonBoard Jobs-Table 1.csv

Includes job descriptions in Spanish:
 Source, Title, Company, Description, Link

### LinkedIn Jobs Dataset: LinkedIn Jobs-Table 1.csv

Includes job descriptions in English:
 company_name, title, description, formatted_work_type, job_posting_url, skills_desc


## Project Workflow

### Data Cleaning and Preprocessing


Removed non-ASCII characters, numbers, punctuation, and stop words.
Standardized text with lowercasing.


### Modeling

Represented job descriptions and candidate skills as vectors using TF-IDF (Term Frequency-Inverse Document Frequency).
Used Cosine Similarity to measure the similarity between job descriptions and candidate skills and create matches.


### Evaluation

Compared similarity scores and candidates matches for the same job using candidates sourced from the verified and unverified dataset.

### Key Results

#### Finding: Identical matches were produced for both LinkedIn and GetOnBoard jobs with no significant difference in similarity scores, regardless of the candidate dataset used.
#### Observation: LinkedIn Jobs (English dataset) yielded higher similarity scores compared to GetOnBoard Jobs (Spanish dataset). This likely indicates higher keyword matching in the LinkedIn job descriptions compared to the GetOnBoard descriptions.

## Installation and Requirements

Python Version: Python 3.10.12

Required Libraries:
 math, scipy, matplotlib.pyplot, pandas, sklearn, seaborn, re, nltk, numpy
 Install dependencies using:
 pip install pandas numpy scikit-learn matplotlib seaborn nltk



## How to Use

### Cloning a Repository 
1. On GitHub, navigate to the main page of the repository.
  - Above the list of files, click <> Code.
  - Copy the URL for the repository.
  - Open Terminal
  - Change the current working directory to the location where you want the cloned directory.
  - Type git clone, and then paste the URL you copied earlier
  - Press Enter to create your local clone.
  - Navigate to cloned directory
  - Create new branch using git branch <branch name>
  - Switch to new branch  git checkout <branch name>
2. Committing Changes
  - Stage the changes git add <file_name>
  - Add all changes git add .
  - Commit the changes git commit -m "Your commit message"
  - Push the branch to the remote repository git push 
3. Prepare the Data
  - Download the provided datasets: stackoverflow_full.csv, GetonBoard Jobs-Table 1.csv, LinkedIn Jobs-Table 1.csv.
  - Upload these datasets along with your verified dataset to your Google Colab instance.
4. Run the Notebook
  - Open the provided .ipynb file in Google Colab.
  - Execute the cells to clean, preprocess, and analyze the data.
5. Customize the Verified Dataset
  - Replace placeholders with your verified dataset for personalized evaluation.

## Future Work

Experiment with alternative data preprocessing methods to ensure equal similarity in english and spanish job descriptions to enhance feature extraction.
Incorporate human evaluators with domain knowledge to assess the matches  using verified vs unverified candidate data
Explore integrating modern large language models (LLMs) for improved candidate to position matching 

## Team and Contribution

Ashley Lopez - Data Cleaning and Preprocessing [filtering non-ASCII characters, numbers, punctuation, and stop words]

Annanta Budhathoki - Modeling [TF-IDF Vectorization]

Sarah Olson - Modeling [creating matches from similarity scores] and Evaluation [comparing matches between candidate datasets]

Audrey Roller - Evaluation [comparing matches between job datasets]

Sarah Baskin - Data Cleaning and Preprocessing [removing NA values from verified and unverified datasets ]


Advisors: George Abu-Daoud, Natalie Gil, Sara Díaz Oporto
