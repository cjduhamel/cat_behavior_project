**Project Proposal: Predicting Cats’ Prey Preference based on the Link between Personality and Owner-Reported Predation Habits**

**1\. Introduction:**  
Our project aims to investigate how the personality traits of domestic cats relate to their hunting preferences, aiming to predict whether a cat is more inclined to hunt birds or small mammals. Using data mining techniques on a large dataset of owner-reported personality profiles and predation habits, we will build a model to classify these preferences based on personality traits like playfulness, aggression,  sociability, etc. Our approach involves supervised machine learning, focusing on multi-class classification. This project builds on existing research connecting animal personality with behavior and aims to provide practical recommendations for cat owners, such as toy selections aligned with each cat's natural instincts. We hope our results could enrich pet care by enhancing our understanding of feline behavior, ultimately supporting pet owners and the pet industry.

**2\. Problem Statement:**  
The aim of this project is to develop a predictive machine learning model that determines the hunting preferences of domestic cats (e.g., preference for ground prey vs. birds) based on individual personality traits and breed characteristics. We propose to solve this problem by formulating it as a supervised multi-class classification task. 

By leveraging an existing dataset that links owner-reported cat personality profiles with predation frequency, this model will provide insights into likely hunting behaviors, which will further serve as a basis for predicting suitable toy types that align with a cat’s natural hunting instincts and preferences. This approach could offer practical applications for pet owners and the pet industry by enhancing toy recommendations that cater to each cat’s unique behavioral tendencies. The model will take as input, a dataset with features that include: personality traits (e.g., aggression, playfulness, sociability), breed characteristics and predation frequency (observed instances of prey type and predation frequency). The model will output a categorical prediction of the preferred hunting target (e.g., "ground prey," "birds"). This output can then be utilized by the user to interpret which types of toys to buy for their cat.

**3\. Data Description:**

* This dataset is from a study conducted in France surveying over 2500 cat owners about the behavior of their cats to attempt to link cat personality to predatory behavior.   
* The data was deposited in a Mendeley Data Repository and retrieved in the form of an Excel spreadsheet.  
* Over 3000 Cats surveyed.  
* This dataset and its features is non-linear, requiring models that can handle non-linear datasets.  
* For Each cat, many features were recorded, including an evaluation of their personality using criteria based on the Feline Five model described by Litchfield et al)   
  * [https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0183455](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0183455)  
* Cat Information Features:  
  * Sex, Age Range, Breed, Number of Cats in Household, Residence Type, Area Type, Time Spent Outdoors, Time spent with cat  
* Cat Personality Features:  
  * (Everything is in French) Shy, Calm, Frightened, Intelligent, Vigilant, Perseverant, Affectionate, Friendly, Solitary, Brutal, Dominant, Aggressive, Impulsive, Predictable, Distracted  
* Cat Predatory Info Features:  
  * Bird Interest/frequency, Small Mammal Interest/Frequency  
  * These features will be our labels, each will be evaluated separately, with separately trained models for each label. The labels are multi-class, each having a value between 0-7. The goal is to classify each cat with an interest value between 0 and 7 inclusive.  
* Preprocessing Steps Required  
  * The Labels and values in the dataset are in French, so they must be translated.  
  * Filling In Missing Values  
    * The dataset has certain features that allow the owner to report “Other” or “Unknown”. For these features, we would need to fill in such values, or remove the feature or row from the model depending on the instance.  
  * No Normalization or Standardization is necessary, as all data is categorical (Numerical data is categorical , ranging between 0-7)  
  * Following EDA, we will need to determine the effect of certain features outside of the model building.  
    * Cats whose owners spend little time with them comparatively may have more inaccurate survey results for personality traits, as they may not know their cats as well.  
    * Cats who live in heavy urban environments may be biased towards certain prey due to the lack of diversity in their environment.  
    * Cats who spend all their time indoors may also be biased towards mice, as mice are more likely to be within reach of the cat where birds would remain outside.  
    * Check for class imbalance: We will use the F1 evaluation metric to evaluate this.  
* Link to the Dataset  
  * Research that Produced the Data: [https://www.researchgate.net/publication/367392811\_Pet\_cat\_personality\_linked\_to\_owner-reported\_predation\_frequency](https://www.researchgate.net/publication/367392811_Pet_cat_personality_linked_to_owner-reported_predation_frequency)   
  * Dataset:  
    * [https://data.mendeley.com/datasets/ht5p5pg7b7/1](https://data.mendeley.com/datasets/ht5p5pg7b7/1) 

**4\. Methodology:**

1. **Data Preprocessing and Feature Engineering:**

   1. **Categorical Encoding:**  As the dataset primarily consists of categorical features (e.g., personality traits, area type, breed), we will employ one-hot encoding or ordinal encoding where appropriate to transform these categories into a format compatible with machine learning algorithms.  
   2. **Handling Potential Biases:**  We will perform exploratory data analysis (EDA) to identify potential biases in the data. For instance, we may segment cats based on the amount of time owners spend with them, urban or rural residency, and indoor/outdoor time to account for variances in predation data accuracy.

2. **Model Selection:** We will train separate models for each label (Bird Interest, Small Mammal Interest) to allow focused predictions for each predatory preference.

   1. **Random Forest Classifier:** Useful for capturing complex interactions between personality traits and hunting behaviors. Decision Tree/Random Forest works on non-linear datasets.  
   2. **Neural Networks (Multi-layer Perceptron):** To capture nuanced patterns in large and complex datasets. Multi Layer Perceptron Model required since the dataset is non-linear.  
   3. **k-Nearest Neighbors (k-NN):** Useful for identifying clusters of similar personality and breed characteristics that align with specific hunting preferences. This algorithm classifies new data points based on the current cluster/neighborhood, handling non-linear data sets well.

3. **Evaluation Criteria:**  
   1. **Accuracy and F1-Score:**  As we have multi-class labels, these metrics will be crucial for assessing the model’s performance in terms of correctly identifying the class and managing class imbalance.  
   2. **Cross-Validation:** We will use k-fold cross-validation to ensure the model generalizes well and reduce the chance of overfitting.  
   3. **Confusion Matrix Analysis:** This will help us understand which classes (0-7 scales) are most challenging for the model and where improvements can be targeted.

4. **Practical Interpretability for Toy Recommendations:** We will analyze how well each model’s predictions can be linked back to toy preferences, ensuring the output can provide actionable insights for pet owners and the pet industry.

By leveraging these data mining techniques and classification algorithms, this project aims to generate a robust model that not only provides reliable predictions of hunting preferences but also adds interpretive value to help users choose toys that resonate with each cat’s natural instincts.

**5\. Team Members:**

* C.J. DuHamel  
* Riley Claire Froomin  
* Brendan Holt  
* Arian Houshmand