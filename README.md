# kickstarter-ml
This is a team project that applies various forms of ML models on Kickstarter dataset

The final combined dataset includes 3500 rows, with 18 key features:
- creator_name / creator_id
- launched_at
- duration
- main_category
- status
- country/city
- currency
- funding_goal
- funding_raised
- fx_rate
- spotlight (TRUE/FALSE)
- staff_pick (TRUE/FALSE)
- backers_count
- source_url
- project name
- blurb (short description of project)
- Number of FAQs 
- Number of comments

Additional text features scraped for text analysis:
- Comments
- FAQs
- Story

Target variable: 
- status of campaign (Successful/Failed) 

Outline of project:
- Scraping and processing raw data (using Selenium and bs4)
- Exploratory Data Analysis
- Feature Engineering
  - For text features: AFINN scoring to analyze sentiments of the texts
  - For numerical features: Log & Boolean transformation to normalize values
  - Categorical features: OHE
 - Text Analysis: identify tokens that lead to project's failure/success
  - CountVectorizer + Naïve Bayes Classifier (accuracy = 71.6%)
  - NLTK (WordNet) & Lemmatization (similar accuracy, but better interpretability)

 - ML modelling (accuracy %)
  - Logistic Regression (88.7%)
  - Support Vector Machine (94%)
  - Decision Tree (95.4%)
  - Random Forest (93.4%)
  - Ensemble Stacking (SVM as meta model | 93.6%) **most preferred model with lowest standard deviation
- Deep learning: Neural network (54.8%)
  - GloVe Embeded layer
  - LSTM Layer
  - Dense Layer
  - Output Layer
