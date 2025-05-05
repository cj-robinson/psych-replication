# Psychology Replication Crisis

Find the story here: [cj-robinson.github.io/replication-crisis](https://cj-robinson.github.io/replication-crisis/)

This was an assignment for our Data Studio class at Columbia Journalism School's Data Journalism program, intended to think about how to create end-to-end data stories about topics of our choosing on deadline.

## Introduction and Goals

This project explores the replication crisis that has gripped the pyschology field for the past 15 years. Attempts to replicate long-held hypotheses were constantly failing due to a confluence of factors explored in the piece. The crisis has spurred a large overhaul in the scientific community as transparency becomes increasingly important.

I've long been equally interested and skeptical of pop pyschology. I (maybe embarrasingly) remember attempting to power pose before interviews after seeing Amy Cuddy's TED Talk, and I was very intrigued reading news about the academic debates surrounding these seemingly 'revolutionary' ideas.

During college, I worked in a pyschology lab attempting to measure how 'priming' participants could change their perceptions, and as I learned more about statistics and testing in work, the more I wanted to know about the publishing system and academia. 

My reporting questions were largely centered around:
1. Just how bad is the replication crisis and how can we measure it? 
2. Does a failed replication have any effect? 
3. How are pyschologists dealing with the fallout? 

## Tools

Scraping and analysis:
- Playwright
- BeautifulSoup
- NopeCHA
- R

Visualizations:
- RAWGraphs
- R/ggplot
- Adobe illustrator
- ai2html
- Javascript/D3 for selection of HTML elements

## Files

1. **analysis/gs_scrape.ipynb** - Playwright/BS scraper for Google Scholar
- note that due to a nan value in my list of citations, the scraper failed midway through on the first one. instead of rerunning completely, I restarted halfway through the list since the risk of being banned by Google is high

2. **analysis/replication_open_database.Rmd** - R Markdown file with code to download the dataset and analyze the data for porting into visualization software

3. **data/gs_scrape.csv and data/gs_scape_2.csv** -- the results of the two scrapes of Google Scholar

4. **data/replication_database.csv** - original data retrieved from FORRT

5. **data/replication_citation_df.csv** - data with scraped google scholar results joined

6. **img** - my illustrator files and ai2html outputs, plus a cover photo

## Data Collection and Analysis

1. I downloaded the base dataset using a [R package built by FORRT](https://github.com/forrtproject/FReD). A different version of this dataset is also available on the website, which is what I built the scraper off of initially. 

2. I took the original references in the dataset and used Playwright to loop through the 400 studies and search Google Scholar with each. I would then scrape the first result entry with BeautifulSoup getting title, abstract and citation. 

3. I broke CAPTCHA's using Jonathan Soma's [NopeCHA tutorial](https://jonathansoma.com/everything/scraping/solving-captchas-in-playwright-with-nopecha/), launching Playwright with the extension and my API key

4. Exploratory data analysis in R and visualizations on the scatter plot of original vs replication effects, total count of replications and success rate by field. 

5. Adobe Illustrator for responsive design in mobile/smaller device sizes

6. HTML/CSS/JS to make the scrollytelling experience complete, starting with one example of power posing and continuing on to the entire dataset.

## Learnings

This was one project where a single line in the piece took the majority of the analysis time. I was hoping to find that successful replications were cited less often than those that were not successfuls since I had seen research showing this relationship, but sadly that was not the case. 

Scraping Google was a different beast since they're fairly stingy with their scraping policies. I was first going to use a Python package for scraping the site, but soon realized it would be too risky given the amount of searches I was hoping to do plus the metadata I wanted to scrape. Instead, I manually created the scraper so that I could control CATPCHAs and avoid getting my IP banned, which was a success! 

Next time, I'd like to add an interactive element where the reader is able to participate in one of the replicaiton studies and set up a backend to store user data. I'd then love to have user data displayed alongside some granular study data I found (thanks of course to the increased transparency of psychology these days)!

## Thank you for visiting! 

Feel free to get in touch via email or my personal website, [cj-robinson.github.io](https://cj-robinson.github.io).
