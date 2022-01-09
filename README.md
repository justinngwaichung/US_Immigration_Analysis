# Motivation
This analysis is actually done as a course project for *CIS 545*, a graduate-level Big Data Analysis course at Penn.

But it's much more than that! It's a topic that we're personally interested in and that's why we did it, and we did it well with the best project score in the class!

For a long time, immigration policy has been a key subject of political debate in the U.S. As international students ourselves, the U.S. work permit and permanent residency application system can come across as mystifying at times and even frustrating.

We believe a lot of fellow international students share the same concern. Through our analysis, we hope answer some of the following basic factual questions and ultimately help people better understand the immigration system that is in place. That's what motivated our analysis!
* What are the most important determinants of a "successful" immigration application?
* What affects the "waiting time" of an application?
* Is there any noticeable variation in the success rate of applicants of different nationalities?
* Does computer science skills contribute to a higher salary and a higher chance of immigration approval, even if one is not working in the tech industry?

# Data & Methodology
The core dataset we used is Permanent Employment Certification (PERM) application data for 2018-2021.

In a nutshell, PERM is an application that all green card applicants would have to obtain from the Department of Labour (DoL) before they file their Immigrant Application (commonly known as "Green Card").

The PERM data we import contains key information on individual applicants, such as education level, hiring company, geographical location, etc.

We also made use a number of supplemental datasets to classify individuals' occupations and job industries.

Various methodologies have been tested (as evidenced from the code). The most effective model in predicting a PERM application result is a random forest model (with ~97% accuracy).

# Key findings
Our analysis primarily looks at the approval of Permanent Employment Certification (PERM) applications. PERM approval is necessary for a US permanent residency (commonly known as "Green Card") applications.

* On data exploratory level:
  * Firm size appears to be very positively correlated with PERM application approval.
  * Most PERM applications, certified or not, (unsurprisingly) comes from the state of California. Second in place is actually the state of Texas! A booming tech industry there... followed by the state of New York being third in place.
  * Having a degree is all that matters to your wages. Having a bachelor's versus a Master's versus a PhD doesn't make that much a difference, unless you have a JD or went to med school.
  * No evident discrimination based on previous citizenship.
* In predicting approval / denial of a PERM application:
  * Firm size (no. of employees), proposed wage relative to the prevailing wage of the sector, and education level of the applicant appears to be some of the most important determinants.
  * Random Forest model appears to yield the best prediction result (~97% accuracy) which is somewhat intuitive due to the large number of categorical variables inherent to our dataset.
  * Diving deep into individual variables (see section 4.2.4), we observe a seemingly high degree of arbitrariness of how PERM applications are adjudicated.

# How to improve?
* Enlarge the data size to include more years of records. A larger data size can provide an ideal window to instrument time series analysis, which can potentially track down some interesting trends of the features.
* Examine changes in approval criteria across different administrations.
* Dive down into individual states / industries to uncover any state-specific / industry-specific bias. Our data shows that looking at some of the commonly emphasized variables such as wage, current visa status, home country would not be sufficient in making a sound guess on whether a PERM application would be approved.

# How to run?
Everything is self-contained if you're running on Colab.

If the file is run locally, ensure packages have been pip installed and simply run **python3 main.py**.

There is **NO NEED** to download the zip csv files to run the code. They're just pushed to github for transparency's sake.
