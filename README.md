# TravelRecommendation

# Running
- To run the fastest way, open up a kaggle environment, upload all the data files, copy paste the code.
- To run locally, just copy the code, change the location of files, and run. Popular python packages should suffice. Requirements.txt file supplied.
- The producitonzied way would be to have a docker environment with proper requirement.txt and makefiles.

# Preprocess
- While preprocesing there was no NA or Null values which made life easier as there was no Imputation required for such data.
- We did not have any cold start data too. Users that had no visit/like/add_to_list altogether.
- My first idea was to merge all the dataset into one for better handling and easier management, but I was able to work without it.
- For weight to different user interactions, I took the liberty to assign weight to **like** as 1, as a random user can like just out of curiosity or even mistake. Though if we have more data or inferences we can acquire from the app, that would make the model better. **add_to_list** is 2 and **visit** is 3. Though in future, if there is data that somebody has liked a place before, visited and then unliked or removed from list, we can use that data to infer more about the place.
- The test data was created using only few data(20%) from the list_of_places from users.csv, rather than splitting based on different users. Holding out data that they actually visited or liked or added to list, so that we can predict using the model. A better approach would be to have way more data and split based on each individual interactio rather than assuming all the interactions are same.
- Popularity can be added, basically if a lot of users like a place that should take some weight in scoring a recommendation.
- Tuning different weights to interaction_type will lead to a better result. Needs more experimentation

# Model
- The weight to both Collaorative filtering and Content based filtering is 0.5.
- I would like to experiment more models on this. LightFM, DeepFM, Random Forest for hybrid recommendations.


# Evaluation
Recall@K, MAP, Precison@K implemented. Response time calculated has been lower than 500ms.

# Notes
- We are lacking features, if gathering data from user to make features is tough, getting data for the place from public domains to create a description would help in creating a feature where we could use TF-IDF(or similar NLP methodologies) and have a better recommendation system.
- In between multiple interviews and being sick, I couldn't get much time to get around the code and experiment more. If there is more time, let me know, I would work on it more, I should techinically make scripts over a jupyter notebook. But in lieu of time, I fast protoptyoed this.
- This was coded in <1 day, with learning about recommendations engine. There is a lot more that can be improved about the code.
- There's a lot of error handling that can be introduced to the code. - WOOPS
- Given more time I would look more into interaction matrix and how I can make it more useful apart from in SVD.
