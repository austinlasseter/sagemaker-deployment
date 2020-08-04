Create and Deploy a Trained Model
Before you can deploy a custom PyTorch model, you have to take one more step: creating a PyTorchModel. In earlier exercises, you could see that a call to .deploy() created both a model and an endpoint, but for PyTorch models, these steps have to be separate. PyTorch models do not automatically come with .predict() functions attached (as many Amazon and Scikit-learn models do, for example) and you may have noticed that you've been given a predict.py file in the source directory. This file is responsible for loading a trained model and applying it to passed in, numpy data.

Now, when we created a PyTorch estimator, we specified where the training script, train.py was located. And we'll have to do something very similar here, but for a PyTorch model and the predict.py file.

EXERCISE: Instantiate a PyTorchModel
You can create a PyTorchModel from your trained, estimator attributes. This model is responsible for knowing how to execute a specific predict.py script. And this model is what you'll deploy to create an endpoint.

Model Parameters
To instantiate a PyTorchModel, (documentation, here) you pass in the same arguments as your PyTorch estimator, with a few additions/modifications:

model_data: The trained model.tar.gz file created by your estimator, which can be accessed as estimator.model_data.
entry_point: This time, this is the path to the Python script SageMaker runs for prediction rather than training, predict.py.
In the exercise notebook, you've been given the following code to fill in:

%%time
# importing PyTorchModel
from sagemaker.pytorch import PyTorchModel

# Create a model from the trained estimator data
# And point to the prediction script
model = None
EXERCISE: Deploy the trained model
Deploy your model to create a predictor. We'll use this to make predictions on our test data and evaluate the model.

%%time
# deploy and create a predictor
predictor = None
Evaluate your Model
After deploying your model, you have been given some code to evaluate its performance according to a variety of metrics!

Remember to delete your predictor endpoint after you've finished evaluating the model.

Try to complete these steps on your own, and I'll go over one solution, next!
