# Setting Up AWS Bedrock with virtual environemnt

This README provides instructions for setting up your Python environment, configuring AWS IAM credentials, and running  code by calling different FM like llama2,stablediffusion model by calling it as API from AWS. Follow these steps to get started:


# Exploring Amazon Bedrock: Accessing Foundation Models as an API in a Virtual Environment

## Introduction

As the field of artificial intelligence (AI) continues to evolve, developers seek efficient ways to leverage powerful pre-trained models for various tasks. Amazon Bedrock provides a seamless solution by offering access to a diverse range of high-performing foundation models (FMs) through a simple API. In this post, we'll delve into the world of Amazon Bedrock, explore how to set up your environment, configure IAM credentials, and run code using these foundation models.

## What Is Amazon Bedrock?

Amazon Bedrock is a game-changer for developers working with AI models. Here's why:

1. **Foundation Models (FMs)**:
   - Amazon Bedrock provides access to leading foundation models, including those developed by AI21 Labs, Anthropic, Cohere, Meta, Stability AI, and Amazon Titan.
   - These FMs cover various domains, from natural language processing (NLP) to image generation.

2. **Simplified API Access**:
   - With Amazon Bedrock, using foundation models becomes as easy as making an API call.
   - No need to worry about complex setup or model deployment—just focus on your use case.

3. **Customization Options**:
   - You can experiment with different FMs using interactive playgrounds.
   - Evaluate models based on predefined metrics or set up human evaluations for subjective criteria.

4. **Fine-Tuning and Customization**:
   - Fine-tune FMs using your labeled examples to create specialized models.
   - Securely adapt models to your specific tasks without compromising data privacy.


## Create a Python Virtual Environment

```bash
conda create -p venv python==3.10 -y
conda activate venv
```

## Configure AWS IAM Credentials

1. **Configure IAM in AWS Console**:
   - Log in to the [AWS Management Console](https://aws.amazon.com/console/).
   - Set up an IAM user with the necessary permissions (user with policy to access aws bedrock and get the access key ID,secret access key by opting as below).
     ![image](https://github.com/Sivaneni/AWS-Bedrock/assets/20778407/aea74b6a-79bb-4ff5-8c2f-c95ef1bf799e)
   



2. **Install Required Python Packages**:
   - Ensure that you have installed the required packages (such as `boto3` and `awscli`) by running:
     ```bash
     pip install -r requirements.txt
     ```

3. **Configure AWS CLI**:
   - Run the following command to configure your AWS credentials:
     ```bash
     aws configure
     ```
   - Provide your **access key ID**, **secret access key**, **region**, and **output format**.

4. **Grant Access to Necessary AWS Services**:
  - get access to model
     ![image](https://github.com/Sivaneni/AWS-Bedrock/assets/20778407/4e5aedb8-05ca-41c2-86cd-68310e083b9c)

5. **Sample Code Files**:
   - Check out the following sample code files:
     1. `llama2.py`
     2. `stablediffusion.py`

6. **Run Your Code**:
   - Execute the Python script from your environment:
     ```bash
     python stablediffusion.py
     ```

7. **Deactivate the Environment**:
   - When done, deactivate the virtual environment:
     ```bash
     conda deactivate
     ```

8. **Remove the Environment (if needed)**:
   - If you want to remove the environment completely:
     ```bash
     conda env remove --name venv
     ```

9. **Before Pushing to Git**:
   - Ensure that your `~/.aws/credentials` file contains the `aws_access_key_id` and `aws_secret_access_key`.
   - If not, you may encounter the following error when pushing to Git:
     ```
     error: GH013: Repository rule violations found for refs/heads/main.
     ```
