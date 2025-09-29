# Table of Content


# LLM-Enhanced Processing for Complex Spatial Queries

This project aims to build an interpretable and tool-augmented LLM-based system for answering complex spatial queries. This repo contains the code implementation for:
  - A Melbourne-scale geospatial QA (Question-ansering) benchmark dataset built on Google Maps data.
  - A 2-stage LLM-planner for reliable, verifiable geospatial question decomposition and
  - A small-scale experiments (with 180 test queries) on the LLM-planner performance against our benchmark dataset.

## Dataset Generation Workflow
We employ a modular, scalable dataset generation workflow outlines as the follow:

[![View PDF](images/your_image.pdf)](images/your_image.pdf)

## System Architecture
Out LLM planner:

[![View PDF](images/your_image.pdf)](images/your_image.pdf)

## Setup

### Prerequisite

1. Python 3.11 or higher
2. An venv with all required libraries installed
3. An access key to Google Maps API" `google_maps_api_key`
4. An access key  to OpenaI API: `openai_api_key`

### 1. Clone Repository
`git clone https://github.com/haoyeye5/COMP90055_Research_Project.git`

### 2. Environment Variables
Create a `.env` file in the root directory with the following keys:
openai_api_key=your_OPENAI_key
google_maps_api_key=your_GOOGLE_MAPS_key

### 3. Virtual Environment & Required Libraries

Run:

`python -m venv geoqa`

`source venv/bin/activate` 

`pip install -r requirements.txt`

### 4. Run Dataset Generation

Download the following open datasets from the Australian Beureau of Statistics (ABS):

  [1] Greater Capital City Statistical Areas - 2021 - Shapefile (url: https://www.abs.gov.au/statistics/standards/australian-statistical-geography-standard-asgs-edition-3/jul2021-jun2026/access-and-downloads/digital-boundary-files)

  [2] Population estimates by SA2, 2001 to 2024, GDA 2020, in GeoPackage  (url: https://www.abs.gov.au/statistics/people/population/regional-population/latest-release)
  
Create a folder: `raw`, put [1] and [2] into this folder. Create a folder: `curated`, at the same directory as `raw`. Put both folder in the same directory as the `notebook` folder.
Run all code blocks in `notebook/dataset_construction.ipynb`

### 4. Run LLM  Planner 
Run all code blocks in `notebook/system_implementation.ipynb`

### 5. Run Experiments
Run all code blok=cks in `notebook/experiment_graphs.ipynb`


## Experiments

### Case Study 
The following map shows an instance in our benchmark dataset dataset. The query is: 

### Experiments Results
We evaluate our LLM Planner on 180 tests data from our benchmark dataset. Below are experiment results on 4 standard metrics:


   
   
