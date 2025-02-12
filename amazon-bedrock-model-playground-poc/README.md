# Amazon-Bedrock-Model-Playground-POC

This is sample code demonstrating the use of Amazon Bedrock and Generative AI to implement a Gen AI model playground. The application is constructed with a simple streamlit frontend where users can input zero shot requests and select any LLM offered by Amazon Bedrock.

![Alt text](images/demo.gif)
# **Goal of this Repo:**

The goal of this repo is to provide users the ability to use Amazon Bedrock and select any of the available Amazon Bedrock LLMs to ask zero shot requests.
This repo comes with a basic frontend to help users stand up a proof of concept in just a few minutes.

The architecture and flow of the sample application will be:

![Alt text](images/architecture.png "POC Architecture")

When a user interacts with the GenAI app, the flow is as follows:

1. The user selects the Amazon Bedrock Model they want to use and makes a "zero-shot" request to the streamlit frontend. (app.py).
2. The application takes the question and the model chosen and routes it to the appropriate model (model_invoker.py). All specific model invocations are stored in (model_selector.py).
3. The final answer is generated by the Amazon Bedrock Model chosen and displayed on the frontend application (app.py).

# How to use this Repo:

## Prerequisites:

1. Amazon Bedrock Access and CLI Credentials.
2. Ensure Python 3.10 installed on your machine, it is the most stable version of Python for the packages we will be using, it can be downloaded [here](https://www.python.org/downloads/release/python-3100/).

## Step 1:

The first step of utilizing this repo is performing a git clone of the repository.

```
git clone https://github.com/aws-samples/genai-quickstart-pocs.git
```

After cloning the repo onto your local machine, open it up in your favorite code editor. The file structure of this repo is broken into 4 key files,
the app.py file, the model_invoker.py file, the model_selector.py file, and the requirements.txt. The app.py file houses the frontend application (a streamlit app).
The model_invoker.py file houses the simple logic of the application to help orchestrate which model should be invoked based on the users selection.
The model_selector.py houses the logic required to invoke the specific model chosen by the end user and generate the final response.
The requirements.txt file contains all necessary dependencies for this sample application to work.

## Step 2:

Set up a python virtual environment in the root directory of the repository and ensure that you are using Python 3.10. This can be done by running the following commands:

```
pip install virtualenv
python3.10 -m venv venv
```

The virtual environment will be extremely useful when you begin installing the requirements. If you need more clarification on the creation of the virtual environment please refer to this [blog](https://www.freecodecamp.org/news/how-to-setup-virtual-environments-in-python/).
After the virtual environment is created, ensure that it is activated, following the activation steps of the virtual environment tool you are using. Likely:

```
cd venv
cd bin
source activate
cd ../../
```

After your virtual environment has been created and activated, you can install all the requirements found in the requirements.txt file by running this command in the root of this repos directory in your terminal:

```
pip install -r requirements.txt
```

## Step 3:

Now that the requirements have been successfully installed in your virtual environment we can begin configuring environment variables.
You will first need to create a .env file in the root of this POC specific directory within this repo. Within the .env file you just created you will need to configure the .env to contain:

```
profile_name=<AWS_CLI_PROFILE_NAME>
region_name=us-east-1 (region of choice)
```

Please ensure that your AWS CLI Profile has access to Amazon Bedrock!

## Step 4:

As soon as you have successfully cloned the repo, created a virtual environment, activated it, installed the requirements.txt, and created a .env file, your application should be ready to go.
To start up the application with its basic frontend you simply need to run the following command in your terminal while in the root of the repositories' directory:

```
streamlit run app.py
```

As soon as the application is up and running in your browser of choice you can begin asking zero-shot questions against any Amazon Bedrock model of your choice.
