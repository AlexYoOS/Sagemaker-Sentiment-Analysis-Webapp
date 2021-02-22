# Sentiment Analysis with AWS Sagemaker


In this project a web-application was built that allows to binary classify IMDB Movie reviews in either positive or negative.
The [IMDB movie review ](http://ai.stanford.edu/~amaas/data/sentiment/) dataset is popular in research and education.

## AWS Services applied in this project

- Sagemaker
- S3
- Lambda
- API Gateway

### Note on the endpoint

The simple HTML web-application __index.html__ sends the review of the user to the endpoint of the deployed model of Amazon Sagemaker, the endpoint is a common __url__.
Since this project is a demo, and since continuosly running an endpoint on AWS is an ongoing expense, the endpoint is shutdown, and so the web-apps request is not resulting in a response for the time being. In production an endpoint is continuosly run and can be updated without disrupting services.

_Further, before replacing a running model with an update, built-in A/B Testing can be performed to make sure that an update is more effective than the original model._

### Model

This classification task was performed with a Recurrent Neural Network, more precisely, an __LSTM Model__(Long-short term memory).

While in general we expect native Sagemaker Models, such as XGBoost, to outperform to outperform costumary built models, such as ours, for task which can be performed either way, we nevertheless achieved a high accury on the testset, tested with a batch transformation approach in the jupyter notebook.

