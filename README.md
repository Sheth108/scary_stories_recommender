# Recommending Scary Stories Using Natural Language Processing

In this project, I scraped six different types of scary stories from the same thought-catalog.com. These stories range from real life horrible happenings such as true abduction tales to seemingly less true stories involving ghosts and superstitions. The stories were then modeled into different topics, which were then used to create a recommender system for a user. Below is a short description of the purpose of each file.

## Scrape All Stories

A simple scraping function is created to retrieve the html of the chosen website, and after this many different functions were created in order to separate the different stories as well as clean them. Some of the sites required the same functions to clean the stories, and some required different ones. In the end, the stories are all put into a list and pickled to be used for modeling.

## Modeling

The stories are brought in, and each story is filtered that so the only words that remain are the nouns and adjectives (due to these being the most defining parts of scary stories). Another function was created which allows the user to decide between LSA or NMF models, count vectorizer or TFIDF vectorizer, among other features as well. The output then displays the topics and returns the model. Stop words were added accordingly for words that did not contribute to defining different topics, and the four best topic models (ranging from three topics to six topics) were selected in the end. LDA modeling was also given a chance but did not work nearly as well as LSA and NMF.

## Recommender

Multiple different recommenders were tested, and for each of the four topic models. The first recommender involved using cosine distance, and recommended the story which had the shortest cosine distance to the input story. The next recommender used dimension reduction (PCA) on the model probabilities, to give each story two coordinates. The recommended story had the shortest euclidean distance from the original story's PCA dimensions. The final recommender used cosine similarity, however also took into account the website in which the story originated on (as they were scraped from a few different sites). This was determined to output the most similar stories, using the topic model which contained six different topics (which can be viewed in the presentation slides). The remaining code was used to produce visuals, as the average PCA coordinates for the six different topics were calculated and stored in an excel file for easy access from Tableau. The visual at the bottom shows the PCA coordinates of three stories (two of which are similar, one of which is very different), and this can also be viewed in the presentation slides.

## Scary Decision

I gave a brief 5-minute presentation on my findings. These are the slides used to discuss the results.

## topics.csv

This is the excel file which contains the average PCA coordinates for the different topics as well as the number of stories to appear in each topic.