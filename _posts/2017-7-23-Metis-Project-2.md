---
layout: post
title: US House Elections
---

### Introduction
I recently set out to see if I could predict margin of victory for U.S. House of Representatives elections using biographical information about the winning candidates.

I would think that biographical information about individual politicians should have no impact on their margin of victory. Other variables are likely to drown out any influence marriage, children, or education might have on the outcome of the elections. However, humans have a well-documented propensity to bias, so perhaps this bias was influencing how they voted in federal elections.

On the more personal side of things, I've also been interested in improving my web scrapping skills, so I figured this was an excellent oppotunity to improve those as well. To get the biographical details of each current House Representative I scrapped each politician's Wikipedia page for details like number of children, marital status, gender, and education (type of degree). Below is an example of a Wikipedia page that has everything I'm looking for.

![screencap of Representative's Wikipedia page]({{site.url}}/images/wiki_screencap.png)

---
### Scrapping Wikipedia
I used [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/) to scrape Wikipedia, and while there are other more powerful scraping tools out there Wikipedia is relatively straight-forward enough that BS was all I needed.

Web scraping is not an automatic process. It's especially difficult when you're used to turning to programming code to automate and deliver complicated results in a timely fashion. To accurately scrape a given webpage requires digging through the HTML and iterating your BS code until you're able to pluck out the specific piece of data you're targeting.

![screencap of BS code]({{site.url}}/images/bs_code_screencap.png)

### Cleaning & Analyzing the Data
Unfortunately not every politician had all the information I was looking for listed easily on their Wikipedia pages. Sometimes the data wasn't in the right format ("three" listed as number of children instead of the much easier to use "3"). The next step on my journey required getting all of the scrapped data into a single Pandas dataframe and then imputing my missing values (since I was planning on using linear regression to analyze the data).

The next step, once everything was in the right place, was to walk through a linear regression analysis, looking at various features and seeing how they interacted with the target. Below, for example, we can see how three of the features interacted with the target (margin_2016):

![pairplot screencap]({{site.url}}/images/pairplot_screencap.png)

At least from visual inspection, Age and Years in Office appear to have no relationship to the 2016 margin of victory. This is not the case with the last feature, 2014 margin, which appears to have a very strong positive correlation with the target.

Linear regression analysis confirmed that the 2014 margins of victory did indeed go a long way in predicting the margins in 2016. This makes sense intuitively, since districts are likely to vote similarly from election to election.

None of the biographical variables of the candidates were statistically significant. This provides evidence that voters are not particularly prejudiced by the unimportant details of a candidate's life, such as their martial status or particular educational history.

### Project Conclusion
This project accomplished two main things for me: improving my web scrapping skills and better understanding linear regression. While I didn't go into it above, my statistical analysis also involved using more advanced linear regression techniques such as regularization of the model and cross validation of the data.

If I was to consider other investigations related to this data, it might be valuable to see if biographical information influences closely contested elections. In politics it doesn’t really matter whether you win by half a percent or 70%, all that really matters is that you win. So perhaps gathering biographical information on the losers of elections as well as the winners might reveal something that this margin of victory data didn’t.

It also might be worth seeing if the margins change within a district when a new candidate runs. For example, if a white married female Representative was to retire in 2018 and an American-American single male was to run in her place, we could see if his margin of victory differs significantly from historical values and parse out bias that way. 
