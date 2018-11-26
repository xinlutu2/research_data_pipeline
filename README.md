# Data Engineer: Research ETL Case Study
* ETL Python program to fetch research data based on keyword (tobacco in the example) (articles and journals) from [PLOS Search API](http://api.plos.org/solr/examples) and [DOAJ API](https://doaj.org/api/v1/docs#!/Search/get_api_v1_search_articles_search_query), transform the data into a tabular structure (.csv), analyze the data to determine important authors, journals/department for certain research topic
* One sample Airflow pipeline to demonstrate how to convert ETL python program to production data pipeline: extact research data from API -> Flatten to .csv -> Load to S3 bucket 
* The purpose of this python program is concentrated on data engineering practice to fetch data as complete as possible with less focus on analytics. Thus, important/influential authors, journals/department is simply defined as having most number of open access articles 
* Results........

## Prerequisites
1. [Python 3.7](https://www.python.org/)
2. [Virtualenv](https://virtualenv.pypa.io/en/latest/)
	* [Pandas](https://pandas.pydata.org/) 
3. [Jupyter Notebook](http://jupyter.org/)

## Instructions for running the code
1. Run `source env/bin/activate` to activate virtual environment
	* This should open up the Python 3.7 environment with necessary libraries
2. Run `python test.py` to make sure all the unit tests are passed
3. Run `python main.py` to start python ETL program
	* The program consists three parts of research data based on given keyword (tobacco)
		* Fetch research articles from [PLOS Search API](http://api.plos.org/solr/examples)
		* Fetch according research journals information from [PLOS Search API](http://api.plos.org/solr/examples) on journal level
		* Fetch according articles online links from [PLOS Search API](http://api.plos.org/solr/examples) on article level. This provides flexibility for researchers and analysts in case they want to see the full text article (This process might take severals minutes depends on the number of articles. In the example on tobacco research (around 300 articles), takes around 15 minutes)
4. tobacco_research_full.csv for full dataset and tobacco_research_subset.csv for selected relevent fields for analysis will be saved on local file system in the same directory

## Improvements