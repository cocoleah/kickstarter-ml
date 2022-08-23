# Modelling with Kickstarter Dataset
<a href="url"><img src="https://logos-world.net/wp-content/uploads/2020/10/Kickstarter-Logo.png" height="250" width="500" ></a>

This is a team project that applies various forms of ML models on Kickstarter dataset. 

The project aims to find out the potential factors that make a crowdfunding project successful. This way, we would be able to provide insights for individuals to help their projects reach their fullest potential. Additionally, we would be able to help investors predict if a project would be successful, thereby giving them increased confidence for their investments.

The final combined dataset includes 3500 rows. 

Key Features:
- backers_count, the number of backers for the campaign
- blurb, a short blurb (project write-up) below the title
- country, country where the campaign is launched
- currency, the currency of the campaign funding ($, € etc.)
- duration, duration of the campaign in days (deadline - launch date)
- goal, the target amount of funding ($, € etc.)
- launched_at, date of campaign’s launch
- main_category, the main category that the campaign was listed in (e.g. art, music, food)
- name, title for the project
- pledged, the total actual amount of funding raised($, € etc.)
- spotlight (TRUE/FALSE), whether the project was listed in the spotlight when it was active on the kickstarter platform
- staff_pick (TRUE/FALSE), whether the project was chosen as the staff pick and displayed on the “Projects We Love” page when it was active on the kickstarter platform
- source_url, unique url address of campaign
- state, state of campaign (Success, Failed, Cancelled etc.) -- Target variable

Additional text features scraped for text analysis:
- Project comments
- FAQs
- Story

Outline of Project:
- Scraping and processing raw data (using Selenium and bs4)
- Exploratory Data Analysis
- Feature Engineering
  - For text features: AFINN scoring to analyze sentiments of the texts
  - For numerical features: Log & Boolean transformation to normalize values
  - Categorical features: OHE
- Text & Sentiment Analysis: identify tokens that lead to project's failure/success
  - CountVectorizer + Naïve Bayes Classifier (accuracy = 71.6%)
  - NLTK (WordNet) & Lemmatization (similar accuracy, but better interpretability)
- ML Modelling (accuracy %)
  - Logistic Regression (88.7%)
  - Support Vector Machine (94%)
  - Decision Tree (95.4%)
  - Random Forest (93.4%)
  - Ensemble Stacking (SVM as meta model | 93.6%) **most preferred model with lowest standard deviation
- Deep Learning with Neural Network (63.5%)
  - GloVe Embeded layer
  - LSTM Layer
  - Dense Layer
  - Output Layer

Overall, we managed to achieve our end goal of finding out factors that contribute to a higher success rate of a project.
This includes features such as backers count, goal, pledged and average fund per backer. The model we prefer the most
for our project would be stacking as it has the highest accuracy and lowest standard deviation among all the models.

With our best model (stacking) and top features that drive the success rate of projects, we could build real-time
dashboards to track a project’s progress, which would be useful for guiding vested investors with their decision-making
process. Additionally, the model will provide project creators the opportunity to improve their projects along the way,
knowing what features they should focus on to boost their likelihood of success.

Source: Archived Kickstarter projects from https://webrobots.io/kickstarter-datasets/ 
