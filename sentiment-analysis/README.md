# Sentiment Analysis Web App Project

## Project Overview
This is a SageMaker deployment project of sentiment analysis of movie reviews with a recurrent neural network for Udacity ML Engineer certificate. 
The model was created and deployed using Amazon's SageMaker service and the final web app interacts with the deployed model.

- The SageMaker Project.ipynb file includes the code to 
  - Download or otherwise retrieve the data.
  - Process / Prepare the data.
  - Upload the processed data to S3.
  - Train a chosen model.
  - Test the trained model (typically using a batch transform job).
  - Deploy the trained model.
  - Use the deployed model.
- The train folder with all provided files and the completed train.py.
- The serve folder with all provided files and the completed predict.py.

Additionally, an endpoint using API Gateway and a Lambda function were created, both of which are now shown in the repository.

### Workflow

Users give data (e.g. review) to the web app, which can be sent through an endpoint created with API Gateway to Lambda function for pre-processing, and then to the deployed model.
The model performs inference and sends the result back to Lambda function, which conveys it to the web app through an endpoint created by API Gateway.

![image](https://user-images.githubusercontent.com/39967211/232492874-eda55691-c6b0-4bb4-820c-d773fdfe8897.png)


### API Gateway & Lambda

![image](https://user-images.githubusercontent.com/39967211/232492579-abf72b07-8926-4361-b73c-00e7e96b3fa4.png)

- **App**: The web app accepts a review from users and sends the review to an endpoint that can be created with API Gateway.\
In this project, the endpoint is a URL that allows an application and a model to communicate with each other. 

- **API**: API Gateway forwards the data on to the Lambda function 
 
- **Lambda**: The Lambda function receives the user's review and performs text preprovessing (e.g. tokenizing and producing bag-of-words features). 
Then, it sends the processed review off to the deployed model.
  - A Lambda function is an example of a 'Function as a Service'. It lets you perform actions in response to certain events, called triggers. \
    Essentially, you get to describe some events that you care about, and when those events occur, your code is executed.
  - One big advantage to Lambda functions is that since the amount of code that can be contained in a Lambda function is relatively small, you are only charged for the number of executions.
  

- **Model**: Once the deployed model performs inference on the processed review, the resulting sentiment will be returned back to the Lambda function. 
- **Lambda** : The Lambda function will then return the sentiment result back to the web app using the endpoint that was constructed using API Gateway.




