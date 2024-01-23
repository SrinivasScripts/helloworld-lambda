# AWS Lambda HelloWorld Function

This is a simple AWS Lambda function created to demonstrate a basic HelloWorld example using Python.

## Prerequisites

Before you begin, ensure you have the following:

- An AWS account
- AWS CLI installed and configured with necessary credentials
- Python installed on your local machine

## Create HelloWorld Lambda Function

1. **Navigate to AWS Lambda Console:**
   - Go to the [AWS Lambda Console](https://console.aws.amazon.com/lambda/).

2. **Click "Create Function":**
   - Click the "Create function" button.

3. **Configure Function:**
   - Choose "Author from Scratch."
   - Enter a name for your function (e.g., HelloWorldFunction).
   - Select "Python" as the runtime.
   - Choose an existing role or create a new one with Lambda execution permissions.

4. **Function Code:**
   - In the "Function code" section, replace the existing code with the following Python code:

     ```python
     def lambda_handler(event, context):
         return {
             'statusCode': 200,
             'body': 'Hello, this is a HelloWorld Lambda function!'
         }
     ```

5. **Save Function:**
   - Click the "Deploy" button to save your function.

## Test the Lambda Function Locally

1. **Install AWS SAM CLI:**
   - Install the [AWS SAM CLI](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-install.html) on your local machine.

2. **Clone Repository (Optional):**
   - If you haven't already, clone this repository to your local machine.

3. **Navigate to Function Directory:**
   - Open a terminal and navigate to the directory where your Lambda function code is located.

4. **Run AWS SAM Local API:**
   - Run the following command to start a local API Gateway:

     ```bash
     sam local start-api
     ```

5. **Test Locally:**
   - Open your web browser or use a tool like `curl` to send a request to your local API Gateway:

     ```bash
     curl http://localhost:3000/
     ```

   - You should see the response from your HelloWorld Lambda function.

## Deploy Lambda Function to AWS

1. **Package and Deploy:**
   - Run the following command to package and deploy your Lambda function:

     ```bash
     sam deploy --guided
     ```

   - Follow the prompts to configure the deployment. This command will package your function and create/update the necessary AWS resources.

2. **Invoke Lambda Function on AWS:**
   - After deployment, navigate to the AWS Lambda Console.
   - Select your deployed function (HelloWorldFunction).
   - Test the function using the "Test" button in the console.

Congratulations! You have successfully created, tested locally, and deployed a HelloWorld Lambda function on AWS using Python.
