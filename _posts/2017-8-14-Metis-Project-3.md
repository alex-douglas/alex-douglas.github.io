---
layout: post
title: Predicting Drug Use
---

### Introduction
The New York Times recently posted [an article](https://www.nytimes.com/2017/07/24/business/economy/drug-test-labor-hiring.html?_r=2) on the troublesome American companies have been having in hiring workers, due mainly to the failed drug tests that can eliminate as many as 25% or 30% of potential employees. 

What if we could identify these drug users ahead of time -- before the drug test, before even the initial interviews? This would save companies time and money during the hiring process and allow them to bring in only the candidates who are most likely to be successful and productive employees.

So I set about creating a pre-employment application; a basic questionnaire that would ask a potential employee questions about themselves. Most of these questions would be traditional employment related questions typical of any blue-collar job application (height, weight, employment history), but there would also be several non-traditional questions, such as: "How often do you like to test yourself by doing something a little risky?" 

This question came from the 2015 [National Survey on Drug Use and Health](http://datafiles.samhsa.gov/study-dataset/national-survey-drug-use-and-health-2015-nsduh-2015-ds0001-nid16894), which asks survey respondents this question, in addition to lots of other basic demographic and biographic questions. The survey also asks explicitly about drug use, so we can use this dataset to classify people into drug-users and non drug-users.

![survey screencap]({{site.url}}/images/project_3_survey_screencap.png)

### Cleaning the data
While I'd like to include all possible survey questions in my pre-employment application, that would make the application burdensomely long, and more importantly be illegal. As one would expect, there are a number of questions employers are not allowed to ask on a job application (such as sexual orientation). But there are also a number of questions that you can't ask which you might expect to be able to, such as if English is the applicant's native language. (See [here](http://www.comparebusinessproducts.com/fyi/30-interview-questions-you-cant-ask-and-30-sneaky-legal-get) for a good article on the legality of different questions.)

This meant that I had to eliminate a large portion of the questions asked in the National Survey on Drug Use and Health. In the end, I was able to use approximately 30 questions, which, after converting most of these to dummy variables, gave me just over 100 features to use in my classification model.

![Drug Use by Type]({{sit.url}}/images/project_3_drug_use_by_type.png)

### Model Results
Unfortunately, the hypothesis that we could predict drug use based on other basic demographic features was incorrect. 

I ran the data through a number of cross-validated classification models, and only the gradient boosting model produced an accuracy higher than the baseline. My logistic regression model also did quite well, and produced the highest ROC-AUC score, but had a lower accuracy than if we were just to predict all non drug-users for every applicant.

![ROC-AUC]({{sit.url}}/images/project_3_roc_auc.png)

### Follow Up
While the data didn't produce the desired result, this was still an excellent project for examining different classification models and working with Flask to create a web application that interfaces with Python code. 

In a follow up post (or in an edited version of this post) I plan to go into more detail on how the Flask app integrated with the rest of my project and the result of that work.


