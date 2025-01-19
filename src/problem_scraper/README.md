# Codeforces Contest Data Scraper

This project is a Python-based scraper designed to automate the process of collecting problem statements, metadata, and editorials from Codeforces contests. It uses Selenium for browser automation and BeautifulSoup for parsing HTML content.

## Features

- **Directory Setup**: Automatically creates necessary directories for storing metadata, problem statements, and editorials.
- **Problem Metadata Extraction**: Extracts metadata such as problem ID, contest ID, difficulty, tags, input/output specifications, and sample tests.
- **Problem Statement Extraction**: Fetches and saves problem statements in a structured text format.
- **Editorial Link Extraction**: Identifies and retrieves the editorial link for a contest.
- **Editorial Content Extraction**: Extracts and saves editorial content for all problems in the contest.
- **Contest Problem Parsing**: Automatically fetches all problem links from the contest page.

## Prerequisites

1. Python 3.7+
2. Google Chrome browser
3. ChromeDriver (compatible with your Chrome version)
4. Required Python libraries:
   - `selenium`
   - `beautifulsoup4`
   - `lxml`

Install the required Python libraries using:
```bash
pip install selenium beautifulsoup4 lxml
```

## Directory Structure

The script creates the following directory structure:
```
data/
├── metadata/
├── problem_statements/
└── editorials/
```

- **metadata/**: Stores problem metadata in JSON format.
- **problem_statements/**: Contains problem statements as text files.
- **editorials/**: Saves editorial content for problems as text files.

## Usage

1. Update the `cont_link` variable in the script with the link to the desired contest.
2. Run the script:
   ```bash
   python scraper.py
   ```
3. The script will scrape the contest data and save it in the `data` directory.

## Key Functions

### `create_directories()`
Creates necessary directories for storing metadata, problem statements, and editorials.

### `extract_problem_id(input_string)`
Extracts the problem ID from a problem title.

### `extract_name(input_string)`
Extracts the problem name from a problem title.

### `extract_contest_id(input_string)`
Extracts the contest ID from the contest URL.

### `find_question_details(question_link)`
Extracts and saves the problem statement and metadata for a given problem link.

### `extract_editorial_link(question_link)`
Finds and returns the editorial or tutorial link for the contest.

### `extract_editorial_content(link_editorial, problem_names)`
Scrapes and saves the content of the contest's editorial for each problem.

### `get_all_prob(contest_link)`
Fetches all problem links for the given contest.

## Example

For the contest at `https://codeforces.com/contest/1844`, the script will:
1. Scrape all problems and their details.
2. Save the metadata and problem statements in the respective directories.
3. Extract and save the editorial content.

## Notes

- Ensure that ChromeDriver is installed and added to your system's PATH.
- The script handles math expressions (`<span class="math">`) by removing them from the content.
- Be cautious of dynamic page load times; adjust Selenium waits if needed.



