# twitterRnalysis
Documentation of how to do data collection and analysis of tweets

1. Install required software<br/>
2. Scraping<br/>
3. Data manipulation in R and export to Microsoft Excel<br/>

# Two ways to scrape Twitter:
1. Using Twitter own API via a package in R (limited to tweets from the last 5-6 days
2. Using Python script written by @Jefferson-Henrique (no limitations)

## Method 1: Using the Twitter API in R

### Install R and RStudio    
1. [Download R](https://cran.r-project.org/)
2. [Download RStudio](https://www.rstudio.com/products/rstudio/download/)
3. Install packages for R:<br/>   
    - twitteR, tidytext, dplyr, ggplot2, stringr, data.table, tm, wordcloud, syuzhet, devtools, widyr, tidyr, igraph, ggraph
    - ex: `install.packages("twitteR")`

### Process
1. Setup Twitter account
    - Validation process might take a few days
    - Guide on how to get developer access can be found [here](https://towardsdatascience.com/access-data-from-twitter-api-using-r-and-or-python-b8ac342d3efe) 
2. Open the twitter.Rmd file (this repository)
3. Replace the API keys and access tokens in chunk 1 of the Rmd file with the information from your Twitter developer account.
4. Run chunk 1
5. Define search parameters in chunk 2
6. Run chunk 2
7. Run chunk 3 to save the file locally as excel.

The Rmd-file also includes chunks with which you can produce wordclouds, carry out sentiment analysis and do network (collocation) analysis of word pairs. 


## Method 2: Using Python

### Install Python on Windows:
1. [Download](https://www.python.org/downloads/release/python-2715/) <br/>
2. Open Command Prompt (on some corporate networks you need to run the command prompt as administrator)
3. `setx PATH "%PATH%;C:\Python27\Scripts"`

### Install Python on Mac:
1. Install Xcode tools <br/>
    1. Open Terminal and copy/paste the following code:<br/>
    `xcode-select --install`

2. Install Homebrew <br/>
    1. Paste the following code into the terminal window:<br/>
    `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`
    
    2. Add Homebrew to your path. Paste the following code into the terminal windows: <br/>
    `export PATH="/usr/local/bin:/usr/local/sbin:$PATH"`
  
3. Install Python (2.7) via terminal:<br/>
`brew install python@2`
    1. Add Python to your path:<br/>
    `export PATH="/usr/local/opt/python@2/libexec/bin:$PATH"`

### Install Twitter Scraper
1. Clone or download the [this project](https://github.com/Jefferson-Henrique/GetOldTweets-python)
2. Extract the repository (if you downloaded zip)
2. Open command line tool (Terminal on Mac or Command Prompt on Windows). 
3. Navigate to where you cloned/extracted the GetOldTweets program.
4. You can start getting tweets usinge the command line:
    - `python Exporter.py --username sometwitteruser`
    - You can also search for topics:
    - `python Exporter.py --querysearch "some great topic"`
5. Output is saved as a CSV-file as `output_got.csv` which can be opened by Microsoft Excel
