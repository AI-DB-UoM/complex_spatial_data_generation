# Table of Content


# LLM-Enhanced Processing for Complex Spatial Queries

This project aims to build an interpretable and tool-augmented LLM-based system for answering complex spatial queries. This repo contains the code implementation for:
  - A Melbourne-scale geospatial QA (Question-ansering) benchmark dataset built on Google Maps data.
  - A 2-stage LLM-planner for reliable, verifiable geospatial question decomposition and
  - A small-scale experiments (with 180 test queries) on the LLM-planner performance against our benchmark dataset.


## Setup

### Prerequisite

1. Python 3.11 or higher
2. An venv with all required libraries installed
3. An access key to Google Maps API" `google_maps_api_key`
4. An access key  to OpenaI API: `openai_api_key`

### 1. Clone Repository
`git clone https://github.com/haoyeye5/COMP90055_Research_Project.git`

### 2. Create Virtual Environment
`

### 2. Install Required Libraries
`pip install req.txt`

### 3. Run Dataset Generation
Download the following open datasets from the Australian Beureau of Statistics (ABS):
Run all code blocks in `notebook/dataset_construction.ipynb`
It will give you 

### 4. Run LLM  Planner 
Run all code blocks in `notebook/system_implementation.ipynb`

### 5. Run Experiments
Run all code blok=cks in `notebook/experiment_graphs.ipynb`


   
   
