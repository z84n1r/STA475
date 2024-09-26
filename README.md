java c
STA475 Assignment #1 (Fall 2024) 
Instructions 
Due date: Friday September 27th at 11:59pm
•  No-questions-asked grace period until Monday September 30th at 5pm
•  No late submissions will be accepted after this time
Where to submit: 
•  Crowdmark:  Submit your answers to each question in correct space on Crowdmark
•  MarkUs  (link: https://markus.teach.cs.toronto.edu/markus/courses/25):   Submit the .qmd file with your answers to Q1 to MarkUs - please just  save a copy of the ques-tions and enter your answers in the space provided. You don’t have to use the .qmd file to answer the other questions if you don’t want to.
•  You can submit as many times as you like before the deadline
•  Email submissions will NOT be accepted
•  Let me know if you’re not able to access the  Crowdmark and/or MarkUs submission sites by September 23rd.
Other notes: 
•  For some questions, you will need to use R; please include all code and relevant output in the pdf submission (make sure the code is visible in the pdf and doesn’t run out of the margins).  If the question asks you to answer a question based on R output, make sure your answer is easy for your TA to find (i.e. start with your answer, then have the code and output afterwards for reference).  Your TA should be able to understand your answer without looking at your and output (as appropriate), but may refer to these to better understand what you did.
•  While you may discuss questions with your classmates, you MUST submit independent work that you did yourself.  Students submitting identical solutions  (e.g. identical sen- tences, derivations steps, or chunks of code) will be investigated for violations of academic integrity.
•  If   you   believe   you’ve   found   a   typo   or   error   in   the   assignment,   please   email sta475@utoronto.ca  so  I  can  look  into  it  and  get  back  to  the  class  as  quickly  as possible.
Question 1 [10 points] 
Note: Parts (a) to (d) will be graded on MarkUs and part (e) will be graded manually on Crowdmark.  Please submit all answers to  Crowdmark (including parts a - d) Understanding the shelf life of fresh fruits and vegetables is key for optimizing storage, pack- aging, and transportation, helping reduce food waste and ensure fresh products for consumers. In this question, we’ll assume the time to spoilage of a fresh produce item follows an exponen- tial distribution with mean 5 days.  Suppose we consider a sample of 2000 fresh produce items under this distribution, and observe them until 60%  (1200 items) have spoiled and become unfit for sale, at which point the observation process will end.
(a) Use R to simulate data for the process described above, generating a tibble named sim with the following columns: T and delta.  Make sure your code  is commented so that someone reading your code can understand what you were trying to do.  Sort the sim tibble in increasing order of T (hint:  you may find the arrange() function useful for this).
library(tidyverse)
SEED <- 1 # DO NOT CHANGE THIS LINE
set.seed(SEED)    # DO NOT CHANGE THIS LINE
n <- 2000
## Q1a 
sim <- NULL # REPLACE NULL WITH YOUR ANSWER
Q1a_dataframe_with_T_and_delta <- sim # DO NOT CHANGE THIS LINE head(Q1a_dataframe_with T and_delta)  # DO NOT CHANGE THIS LINE
NULL
(b) Modify the tibble you generated in the previous part to add a column named X which records the observed response for each observation.  Your updated sim tibble should now have 3 columns: T, delta and X. Don’t change the order of the rows, compared to part (a).
# Q1b: Modify the `sim` tibble
Q1b_dataframe_with_X <- sim # DO NOT CHANGE THIS LINE
head(Q1b_dataframe_with_X) # DO NOT CHANGE THIS LINE
NULL
(c) Based on your simulated values, how long do you need to monitor the 
process to observe 1200 failures?  Save your exact answer (no rounding) to the variable Q1c_study_duration_1200_failures.
# Q1c
Q1c_study_duration_1200_failures <- NULL # Replace NULL with your answer
Q1c_study_duration_1200_failures          # DO NOT CHANGE THIS LINE
NULL
(d) Based on your simulated values, compare the means of x and T in one sentence (you should report the numerical values for these means).  Save the exact values of each mean (no rounding) in the variables Q1d_mean_X and 
Q1d_mean_T.
# Q1d
Q1d_mean_X <- NULL # Replace NULL with your answer
Q1d_mean_T <- NULL # Replace NULL with your answer
Q1d_mean_X          # DO NOT CHANGE THIS LINE
NULL
Q1d_mean_T          # DO NOT CHANGE THIS LINE
NULL
(e) Using properties of the exponential distribution, derive the expected monitoring time required to observe 1500 failures. 
Question 2 [10 points] To answer the  questions below,  refer to the article titled  “Similar rate of return to  sports activity between posterior-stabilised and cruciate-retaining primary total knee arthroplasty代 写STA475 Assignment #1 (Fall 2024)
代做程序编程语言 in  young  and  active  patient”.   This  paper  describes  a  study  comparing  two  types  of knee replacement surgury:  posterior-stabilized and cruciate-retaining.   Note:  You don’t need to read the whole article,  but should focus on relevant aspects of the  Statistical analysis and results sections.
(a) This paper describes several response variables and analyses.  One of the 
analyses is a time-to-event analysis (see Figure 4). What is the response in this time-to-event analysis?  Be as specific as possible (including units). 
(b) Based on Figure 4, when did the last observed failure event occur in the PS group (it’s OK to just say between 10 and 20 months, for example, based on the tickmarks shown on the x-axis).  Explain how can answer this question based on the K-M plot only. 
(c) What is potentially misleading with the visualization in Figure 4?  Do you agree with the authors’ choice? 
(d) Consider the Kaplan-Meier curves in Figure 4.  Interpret and compare the 
estimates of s(t) for the posterior-stabilized and cruciate-retaining groups at 90 months.  Use R to obtain  Kaplan-Meier estimates for each group separately for the data in the knees tibble, and provide exact values of the estimates for each group to use in your interpretation.
knees <- read_csv("knees.csv", col_types = "cdddcccdddcddddddcdddd")
(e) Based on the data in the knees tibble you used in the previous part, calculate the Nelson-Aalen estimate for the 5-year cumulative hazard for the posterior-stabilized group.  Compare this to the estimate of H(t) obtained by transforming the K-M estimate of the 5-year survival probability.  Which approach would you prefer to use in this case and why? 
Question 3 [11 points] The data below summarises the number of weeks 5 individuals spend collecting unemployment insurance before starting a new job.  Some of the individuals are lost to followup before starting a new job, and their follow-up times are denoted with +.ID    Weeks collecting EI 
1 
2 
2 
3+ 
3 
10 
4 
11 
5 
14+ 
(a) In this part, you will calculate K-M estimates and their variances by hand (not using R). Construct a table reporting tj , rj , dj , S(t), and ur(S(t)).  Show your work, not just your final answers. 
(b) Use R to produce a table showing the K-M estimates of the survival probabilities and estimated standard errors of these estimates to check your work from part (a). 
(c) Estimate the 33d percentile (t0.33 ) of the time spent on unemployment based on our 
sample.  Explain how you obtained your estimate. 
(d) Use the log-log transformation to calculate an approximate 95% CI for S(10).  Show your work, specifically (i) how you substitue values into the appropriate variance formula, (ii) calculating a CI of the transformed estimand, and (iii) the final confidence interval. Note:  it is true that the sample size here is very small, but construct the confidence interval nonetheless. 
Question 4 [5 points] 
Consider a discrete failure time response T , with distinct failure times a1  < a2 < … < an (no ties), where aj < t ≤ aj+1 and a0 = 0.
(a) Prove that P (T > aj |T > aj — 1 ) = 1 — h(aj ), where h(t) is the hazard function. 
(b) Prove that S(t) = Πaj≤t  [1 — h(aj )]
(c) Prove that P (t = am ) = h(am ) Πaj≤am — 1 (1 — h(aj ))
Question 5 [5 points + 1 bonus (max 100% on this assignment)] Find a peer-reviewed journal article where the response of interest is a time-to-event response. This should not be an article mentioned in any of our course materials or examples.  For one bonus mark on this question, find an article where the data underpinning the article is also available to download.  The University of Toronto Libraries have a number of databases you can use to search for research articles, for example WebOfScience 
(a) Provide a reference for the article you selected (including the title, authors’ names, journal, and date of publication).  You must also submit either a link to the article (make sure it will work for the grader by testing it in an incognito 
browser) or pdf of the article.  In each of the parts below, indicate where you found your answer in the article (page/section/paragraph number). 
(b) What is the time-to-event response?  Be as specific as you can (include units). 
(c) What kind of censoring are the responses subject to.  Give a specific example of a reason an observation would be considered censored in this study. 
(d) What method(s) are used to analyze the time-to-event response in your article? 
(e) What is one thing mentioned in the methods section of your article that you found interesting and would like to learn more about. 
Bonus:  Is data available for the article you found in Question 5?  If yes, indicate where it can be found (URL or instructions) and submit the data to Quercus at this link. 

         
加QQ：99515681  WX：codinghelp
