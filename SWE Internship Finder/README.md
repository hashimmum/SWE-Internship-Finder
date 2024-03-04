IMPORTANT NOTICE

Just so you know, LinkedIn isn’t a fan of scraping. Use this tool wisely, maybe with a proxy/vpn to keep under the radar. Also I have used this to find almsot all the applications I have submitted and it has neatly tracked them.

Problem

The job market is tough right now, especially for people in tech. Big companies are letting go of a lot of workers, and it's hard to find new jobs because not many places are hiring. For those studying or working in Computer Science, this problem is really hitting hard. Searching for jobs on places like LinkedIn, Google, other job boards can be super frustrating. You keep seeing the same job ads over and over, and you have to wade through a lot of jobs that don't match what you're looking for. Plus, sometimes you apply for jobs and never hear back. Our system is here to help with that. It's a tool that finds job listings from LinkedIn and puts them in one place so you can easily see them. You can filter these jobs to only see the ones that match what you're looking for, like the right job title or the keywords you care about. This means no more seeing jobs you don't want, and it makes finding the right job a lot easier.

Requirements

Flask
Pandas
Requests
BeautifulSoup
SQLite3
Pysocks
Python 3.6 or higher
Installation

Clone the repository to your local machine.
Install the required packages using pip: pip install -r requirements.txt
Create a config.json file in the root directory of the project. See the config.json section below for details on the configuration options. Config_example.json is provided as an example, feel free to use it as a template.
Run the scraper using the command python main.py.
Run the application using the command python app.py.
Open a web browser and navigate to your local host.
Config

The settings.json document serves as a blueprint for configuring the data harvesting tool and its user interface. The configuration options are detailed as follows:

-request_headers: Specifies the headers that should be included with each request. It's essential to set a User-Agent header with a valid string. If unsure about what your user agent is, a quick search online with "what is my user agent" can reveal it.

-proxy_settings: These settings detail how to configure proxies within the requests framework. Both http and https proxies can be set with their corresponding URLs.

-API_key_OpenAI: This is where you enter your OpenAI API key, obtainable through your OpenAI account dashboard.

-model_name_OpenAI: Indicates which OpenAI model to employ for generating cover letters. The GPT-4 series is recommended for optimal results, despite being the costlier option.

-document_path_resume: The path to your resume stored locally, which must be in pDF format. For accurate parsing by the AI, ensure the resume is single-column, devoid of images, and aware that --multi-column layouts may lead to inconsistent outcomes.

-job_search_parameters: Contains objects for each search query, including:

-search_keywords: Keywords to look for within job titles.

-job_location: The geographic location for job searches.

-work_type_filter: Specifies the job arrangement, where 0 is onsite, 1 is hybrid, 2 is remote, and an empty value indicates no preference.

-exclude_description_keywords: Keywords to omit job postings based on their descriptions.

-include_title_keywords: Filters job postings to include those with specified keywords in the title. Leave blank for no title-based filtering.

-exclude_title_keywords: Keywords to exclude certain job postings based on their title. Empty means no exclusions based on title.

-block_company_keywords: Excludes job postings from specific companies. This is for avoiding companies not aligned with your values.

-language_preferences: Automatically filters job postings based on language, using a list of language codes (e.g., "en" for English). Leave blank to avoid language-based filtering.

-search_timespan: Defines the time frame for job postings to consider, with formats like "r604800" for the past week.

-database_table_jobs: Names the database table for storing job postings.

-database_table_filtered_jobs: Names the table for storing selected job postings after filtering.

-database_file_path: The path to the SQLite database file.

-scrape_pages_count: The number of web pages to scrape for each query.

-scrape_cycles: The frequency of scraper runs to capture a diverse range of job postings, potentially set as a scheduled task to run periodically.

-scrape_days_limit: Limits the scraping to job postings not older than a specified number of days.

Need to do to make it better

Enhance the user interface to allow search settings customization and to initiate searches directly. Presently, settings adjustments and search operations require manual edits to a JSON file and commands issued via the terminal.