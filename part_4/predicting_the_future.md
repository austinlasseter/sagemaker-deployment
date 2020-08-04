Predicting the Future
Recall that we did not give our model any data about 2010, but let's see if it can predict the energy consumption given no target, only a known start date!

EXERCISE: Format a request for a "future" prediction
Your task is to create a formatted input to send to the deployed predictor passing in my usual parameters for "configuration". The "instances" will, in this case, just be one instance, defined by the following:

start: The start time will be time stamp that you specify. To predict the first 30 days of 2010, start on Jan. 1st, '2010-01-01'.
target: The target will be an empty list because this year has no, complete associated time series; we specifically withheld that information from our model, for testing purposes. For example:
{"start": start_time, "target": []} # empty target
You'll see the following code to complete in the main exercise notebook. Complete the instances and see if you can generate some future predictions. Also, remember to delete your model endpoint when you are done making predictions and evaluating your model.

# Starting my prediction at the beginning of 2010
start_date = '2010-01-01'
timestamp = '00:00:00'

# formatting start_date
start_time = start_date +' '+ timestamp

# formatting request_data
## TODO: fill in instances information
request_data = {"instances": [{"start": None, "target": None}],
                "configuration": {"num_samples": 50,
                                  "output_types": ["quantiles"],
                                  "quantiles": ['0.1', '0.5', '0.9']}
                }

json_input = json.dumps(request_data).encode('utf-8')

print('Requesting prediction for '+start_time)
