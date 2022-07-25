# modelling_social_data
Establish the top five trending fashion posts across Instagram in this April 2020 subset.

### TO DO:
Steps:
#### num_days_trending
- [ ] Predict the num_days_trending
    - [ ] Perform PCA on each of the five models (linear, SVR, Nu SVR, Linear with SGD, MLP) and see which one performs best and conclude whether it is better to use PCA or not
    - [ ] Perform cross validation when measuring the original performance of the model (like this we calculate the average which
    is better)
    - [ ] Once the model has been decided (very probable to be linear), check which regularisation method to use (No reg, Ridge, Lasso)
    - [ ] Check if the model has a bias-variance problem
    - [ ] Use Bayesian methods for hyperparameter tuning

#### fashion
- [ ] Check whether there has been an NLP model built to predict fashion

### Problems that I have encountered:
* There's an imbalanced dataset problem

### Stuff to include in the report:
* Why have I used MSE to measure the performance of the model?


### TO DO (Visualisations):
`post_metrics_and_comments`
- [ ] See which posts accounted for the max number of views (also see which accounts it was posted from)
- [ ] See which posts produced the max number of comments (also see which accounts it was posted from)

`hashtag_top_appearances`
- [ ] Select the top posts which were trending the longest
- [ ] See to which accounts these posts were related to
- [ ] Create a df with these posts, the number of days, num_likes, num_comments, num_views

`raw_post_metrics`
- [ ] Create graphs to see how the top_trending posts grew over a four week period

#### Modeling
- [ ] Create a model that predict the number of likes a post is going to have
    - [ ] First only predict the number of likes a post has using: username, date_posted, num_comments
    - [ ] Think about a scheme of how this would be done
    - *Future avenue would be using what is written in the comments to predict the num of likes as well*
    - [ ] Second predict the number of likes a post will in a week using: username, current_likes, days_since_posted (infer from date_posted), num_comments
    - *Future avenue would be using the growth it has had in previous weeks to predict this new growth*

### Details about the project
Three questions need to be answered:
* Why certain modeling architectures would work best here?
* How I would modify them (or not)?
* How you would go about implementing them?

What this project includes:
1. Feature engineering
2. Data engineering
3. Modeling

Three pieces of data:
* `post_metrics_and_comments.csv`: This is your main file.. It includes metrics for Instagram posts including the post url, username, caption, image urls, max likes, max comments, max views (if video), followers of the posting profile, followings of the posting profile, all comments (delimited by the character “|”), and the date of posting.
* `hashtag_top_appearances.csv`: This table includes the amount of days a post was trending across leading streetwear community hashtags on Instagram. Trending, in this case, means appearing in the “top posts” section of certain pre-filtered, trending streetwear hashtags. This table includes the post_url and the associated days_in_hashtag_top_section metric.
* `raw_post_metrics.csv`: This table includes main post metrics collected on certain posts across different times in the four week period to monitor the posts’ growth (intervals between consecutive data collection attempts vary). The table includes the post_url, the num_likes, num_comments and num_views (if video) of the post on date_time_collected (the date & time the data was collected on the specific post).