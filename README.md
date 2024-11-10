# IPL 2024 Match Data Scraping and Analysis
 
This project scrapes IPL 2024 match data from Cricbuzz using Python and organizes the data into multiple Excel sheets for structured analysis. 

## Requirements 
- **Python Packages**: `requests`, `beautifulsoup4`, and `pandas` 
- Install dependencies using `pip install requests beautifulsoup4 pandas`

 ## Data Extraction.
 ## Project Files and Outputs
 - **`IPL2024_Match Links.xlsx`**: Stores each match’s basic details, including match number, team names, and URLs for match details and scorecards. 
- **`IPL2024_Match_information.xlsx`**: Contains comprehensive match information such as date, venue, umpires, toss details, and player squads. 
- **`IPL2024_Match_Date&Time details.xlsx`**: Records each match's date, time, series information, and venue details. 
- **`IPL2024_Innings_Details.xlsx`**: Holds innings details for each match, including batting and bowling statistics. 

## Overview of Data Extraction Steps 

### 1. Match Links Scraping 
- **Purpose**: Extracts basic information and links for each IPL 2024 match. 
- **Process**: 
- Requests the main IPL 2024 matches page from Cricbuzz. 
- Scrapes match links, titles, and team names. 
- Constructs URLs for both match details and scorecards. 
- **Output**: 
- Data is saved in `IPL2024_Match Links.xlsx` with columns for match number, team names (Team1 and Team2), match links, and scorecard URLs. 

### 2. Detailed Match Information Extraction 
- **Purpose**: Collects detailed information for each match, including date, venue, and teams. 
- **Process**: 
- For each scorecard URL, extracts match-level data (date, toss, time, venue, umpires) and team-specific data (roles and player names). 
- Handles any failed page loads gracefully by continuing to the next match if an error occurs. 
- **Output**: 
- Data is saved in `IPL2024_Match_information.xlsx` with columns for date, venue, toss details, time, umpires, match referee, and player squads (playing XI, bench players, support staff for each team). 

### 3. Match Date & Time Details Scraping 
- **Purpose**: Extracts date, venue, and series information for each match. 
- **Process**: 
- Uses the match links to navigate to each match's main page. 
- Parses text to isolate series name, venue, and date & time information. 
- Each match's data is stored in a structured dictionary format before being saved to the Excel sheet. 
- **Output**: 
- Data is saved in `IPL2024_Match_Date&Time details.xlsx`, organizing matches by date, time, series, and venue. 

### 4. Innings Details Extraction 
- **Purpose**: Captures innings data for each match, including key batting and bowling information. 
- **Process**: 
- Navigates to each match’s scorecard and extracts detailed innings statistics. 
- Parses each inning’s data, capturing information like batting performance, bowling details, and scoring progress. 
- **Output**: 
- Data is stored in `IPL2024_Innings_Details.xlsx`, with columns for match title and a comprehensive breakdown of innings details. 

## Execution Instructions 
1. **Run Match Links Scraping**: This will populate `IPL2024_Match Links.xlsx` with basic match information. 
2. **Run Detailed Match Information Extraction**: Uses the scorecard URLs to gather in-depth details and save them in `IPL2024_Match_information.xlsx`. 
3. **Run Match Date & Time Details Scraping**: Populates `IPL2024_Match_Date&Time details.xlsx` with series, date, and venue info for each match. 
4. **Run Innings Details Extraction**: Scrapes innings-specific data and saves it to `IPL2024_Innings_Details.xlsx`. 

## Notes 
- **Error Handling**: The script includes checks for page load success and error messages if a URL fails. 
- **Output Consistency**: Data is saved in consistent formats across Excel sheets, making it easy to use the sheets together for further analysis. 

## Conclusion 
This project effectively organizes IPL 2024 match data into four Excel sheets, providing a structured dataset for data analytics, sports analysis, or detailed match insights.

## Data Transformation
### Input Files
- **`IPL2024_Match_information.xlsx`**: Contains match information scraped from links.
- **`IPL2024_Match_Date&Time details.xlsx`**: Holds match date and time details.
- **`IPL2024_Innings_Details.xlsx`**: Includes innings data with detailed batting and bowling information.

### Output Files
- **`Final_IPL2024_Match_information_updated.xlsx`**: Updated match information with team names, umpires, and venues.
- **`Final_IPL2024_Match_Date&Time_Details.xlsx`**: Structured data with date and time details for each match.
- **`IPL2024_Innings_Details_Modified_Innings.xlsx`**: Processed innings data with batting and bowling splits.
- **`Final_IPL2024_Batting_Innings_Details.xlsx`**: Detailed batting statistics for each innings, including player performance.
- **`Final_IPL2024_Bowling_Innings_Details.xlsx`**: Detailed bowling statistics for each innings, including individual bowler performances.

## Data Processing Workflow

1. **Match Information**  
   - Extracts team names and league information, cleans umpire data, and maps short team codes to full names.
   - Saves output to a structured Excel file with deduplicated values.

2. **Date & Time Details**  
   - Parses match numbers and team names, formats date with year, and standardizes time format.
   - Produces an output file with clear match date and time details.

3. **Innings Details Processing**  
   - Splits data into structured columns for batting and bowling innings.
   - Processes each innings for a match and extracts details for each phase (e.g., power plays, 1st and 2nd innings).

4. **Batting and Bowling Details Extraction**  
   - **Batting**: Parses player stats, extras, and team totals for each inning, creating a comprehensive output for analysis.
   - **Bowling**: Extracts individual bowler data for overs bowled, runs, wickets, and other metrics for each inning.

## Key Features

- **Automated Team Name Mapping**: Short team names are automatically replaced with full names for consistency.
- **Date and Time Formatting**: Standardizes date and time information to facilitate easy sorting and analysis.
- **In-depth Player Statistics**: Extracts individual player performance in batting and bowling for in-depth analysis.
- **Formatted Output**: Clean, structured output files in Excel for seamless integration with other tools or dashboards.

## Requirements
- **Python 3.x**
- **Pandas Library**: For data manipulation and Excel processing.
- **Excel**: For accessing and viewing output files.

## Usage

1. Ensure input files are available at the specified paths.
2. Run each script to process the data sequentially.
3. The processed data will be saved to the designated output files.

## Conclusion
This project provides a comprehensive analysis-ready data set for IPL 2024 matches. The structured outputs can be directly used for further analysis or visualization to gain insights into team and player performances throughout the tournament.
