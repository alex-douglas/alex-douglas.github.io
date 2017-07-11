---
layout: post
title: Metis Project 1
---

The Metis Data Science Bootcamp is a "project-oriented" program. While our instructors do give lectures, the bulk of our learning is done by completing projects which reinforce specific data science concepts. Over the course of 12 weeks we're expected to complete five of these projects and present the results.

12 weeks, five projects. Things move quickly. My program started this past Wednesday (July 5th), and we presented our first projects today. While this was not a lot of time to fully explore the questions asked of us, the pace of the work definitely encouraged focused, rapid learning, not least so that we didn't look like fools when presenting 4-5 days worth of research.

Below is a overview of Project 1 as well as my process as I worked through the problem.

---
### Problem Introduction
My project partner and I were tasked with helping a fictional non-profit, WomenTechWomenYes, explore ways to increase visibility in the greater New York City area in the hopes of increasing donations as well as attendance at an upcoming gala.

We were tasked with using [MTA turnstile data](http://web.mta.info/developers/turnstile.html) to analyze the best subway stations where WomenTechWomenYes should place their volunteers. While we were encouraged to use other data sources if desired, the main idea of the project involved using the data science tools learned in the first days of the Metis bootcamp to clean and analyze this MTA turnstile data.

### Data Analysis
Most of the data analysis was done in a [Jupyter notebook](http://jupyter-notebook-beginner-guide.readthedocs.io/en/latest/what_is_jupyter.html), and involved basic analysis using the <a href="https://en.wikipedia.org/wiki/Pandas_(software)">pandas</a> and [matplotlib](https://en.wikipedia.org/wiki/Matplotlib) libraries (two core libraries that every data scientist needs to know).

![screencap of Jupyter notebook]({{site.url}}/images/project_1_jupyter_notebook.png)  

By parsing the MTA data we were able to come up with daily totals for various stations across a given time frame. Below shows the daily ridership values for three random stations over an approximately one month period:

![screencap of Jupyter notebook]({{site.url}}/images/project_1_jupyter_notebook_2.png)

My partner and I combined this information with demographic data from the [American Community Survey](http://api.census.gov/data/2015/acs5/profile.html) to come up with target stations where our hypothetical non-profit should place their volunteers. We targeted 9 stations that were near demographically ideal residential areas (demographically ideal in this case being places with lots of women and tech industry workers), and 7 stations that were not only near NYC tech hubs but also had significantly higher foot traffic than your random NYC subway station.

![screencap of Jupyter notebook]({{site.url}}/images/project_1_jupyter_notebook_3.png)

### Project Conclusion
Overall I felt like this project provided an excellent introduction to the basics of working with data using python, pandas, matplotlib, and Jupyter. There are dozens of basic commands that a data scientist needs to know to get their data in a consumable form, and while I don't yet have complete mastery of this material I think I've developed the foundations that should allow me to move on to the more challenging data manipulation concepts.

Looking forward, I'm excited to see how we can incorporate statistical analysis to really understand our data. For this project we found many MTA stations that stood out as being good targets for a women-in-tech organization, but do the differences that make these stations good targets pass a statistical significance test? While I'm not sure if I'll return to this project to do additional analysis, I'll be sure to update the blog if I do.
