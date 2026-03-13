# AI Resume Screening Agent (Strict Keyword + Semantic Matching)

## Overview

This project is an **AI-based Resume Screening System** that ranks candidate resumes against a Job Description (JD).
It uses **strict keyword matching combined with semantic similarity** to ensure that resumes from unrelated domains receive very low scores.

Example:
If the JD is for a **Content Creator**, resumes from **Data Science, Mechanical Engineering, or unrelated roles** will automatically receive **scores below 20%**.

The system allows HR teams or recruiters to **upload multiple resumes, paste a job description, and automatically rank candidates**.

---

## Key Features

* Upload **multiple resumes (PDF format)**
* Paste **any Job Description**
* **Strict keyword filtering**
* **Semantic similarity ranking**
* Display **candidate scoreboard**
* Move **Top N resumes to screened folder**
* Handles **N number of resumes**
* Prevents **false high scores from unrelated resumes**

---

## Tech Stack

* Python
* FAISS (Vector similarity search)
* Sentence Transformers (Semantic embeddings)
* PyPDF2 (PDF parsing)
* Pandas (Data processing)
* ipywidgets (Notebook UI)

---

## Project Workflow

1. Upload resumes using the **Upload Resume button**
2. Paste the **Job Description** in the prompt area
3. Click **Check Scoreboard**
4. The system:

   * Extracts text from resumes
   * Extracts keywords from JD
   * Calculates semantic similarity
   * Applies strict keyword filtering
5. Candidates are ranked by **Match % score**
6. Click **Screen Resume** to move **Top N candidates** to the screened folder

---

## Folder Structure

```
project/
│
├── uploaded_resumes/
│   └── All uploaded resumes
│
├── screened_resumes/
│   └── Top ranked resumes
│
├── resume_screening.ipynb
│
└── README.md
```

---

## Installation

Install dependencies before running the notebook:

```bash
pip install faiss-cpu sentence-transformers PyPDF2 pandas ipywidgets
```

---

## How the Scoring Works

The score is calculated using **two mechanisms**:

### 1. Keyword Matching

The system extracts keywords from the Job Description and checks how many appear in the resume.

### 2. Semantic Similarity

Vector embeddings are created using Sentence Transformers and compared using FAISS.

### Final Logic

* If keyword match is **very low**, score is **capped below 20%**
* If keywords match well, score increases using semantic similarity

This prevents resumes from unrelated roles getting high scores.

---

## Example

Job Description: **Content Creator**

| Resume                  | Keyword Matches | Score |
| ----------------------- | --------------- | ----- |
| ContentWriter.pdf       | 15              | 89%   |
| MarketingSpecialist.pdf | 6               | 43%   |
| DataScientist.pdf       | 0               | 12%   |

---

## Skills Demonstrated

* Natural Language Processing
* Resume Parsing
* Semantic Search
* Vector Databases
* AI-based Recruitment Automation
* Machine Learning Applications in HR

---

## Future Improvements

Possible upgrades:

* AI skill extraction from resumes
* Candidate summary generation
* Interview recommendation system
* RAG-based resume reasoning
* Integration with HR platforms

---

## Author

Developer: Kajal Dadas
Email: [kajaldadas149@gmail.com](mailto:kajaldadas149@gmail.com)
contact: +917972244559

