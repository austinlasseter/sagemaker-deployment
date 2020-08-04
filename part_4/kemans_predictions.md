Getting Predicted Clusters
After you've trained your KMeans estimator, you can deploy it and apply it to our data to get resultant clusters.

EXERCISE: Deploy the k-means model
Deploy the trained model to create a kmeans_predictor.

%%time
# deploy the model to create a predictor
kmeans_predictor = None
EXERCISE: Pass in the training data and assign predicted cluster labels
After deploying the model, you can pass in the k-means training data, as a numpy array, and get resultant, predicted cluster labels for each data point.

# get the predicted clusters for all the kmeans training data
cluster_info=None
If you finish this exercise, you should be able to proceed with some interesting visualizations that give you the ability to explore how counties are clustered and what that means as far as features that define the similarity between counties.

Shutting Down the Endpoint
After you successfully make predictions and assign each county to a cluster, you can delete your KMenas endpoint.
