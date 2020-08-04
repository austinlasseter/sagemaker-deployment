Instantiating a DeepAR Estimator
Some estimators have specific, SageMaker constructors, but not all. Instead, you can create a base Estimator and pass in the specific image (or container) that holds a specific model. The container for the DeepAR model can be gotten as follows:

from sagemaker.amazon.amazon_estimator import get_image_uri

image_name = get_image_uri(boto3.Session().region_name, # get the region
                           'forecasting-deepar') # specify image
Now that you have the correct image, you can instantiate an Estimator. You're given the following, in-notebook exercise.

EXERCISE: Instantiate an Estimator
A generic Estimator will be defined by the usual constructor arguments and an image_name.

You can take a look at the estimator source code to view specifics.

If you complete this task, you can move on to setting DeepAR's model and training hyperparameters and call .fit() to start a training job! You're encouraged to keep going, deploying and evaluating the model on your owm; you are welcome to consult the solution videos to see if your answer matches mine.
