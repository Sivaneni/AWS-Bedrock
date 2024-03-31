
Create a Python Virtual Environment
conda create -p venv python==3.10 -y
conda activate venv

Configure AWS IAM Credentials
Configure IAM in AWS Console:
Log in to the AWS Management Console.
Set up an IAM user with the necessary permissions
Install Required Python Packages:
Ensure that you have installed the required packages (such as boto3 and awscli) by running:
pip install -r requirements.txt

Configure AWS CLI:
Run the following command to configure your AWS credentials:
aws configure

Provide your access key ID, secret access key, region, and output format.
Grant Access to Necessary AWS Services:
In the AWS Console, grant access to all the services (e.g., S3, Lambda) that your Python code will interact with.
Sample Code Files:
Check out the following sample code files:
llama2.py
stablediffusion.py
Run Your Code:
Execute the Python script from your environment:
python stablediffusion.py

Deactivate the Environment:
When done, deactivate the virtual environment:
conda deactivate

Remove the Environment (if needed):
If you want to remove the environment completely:
conda env remove --name venv

Before Pushing to Git:
Ensure that your ~/.aws/credentials file contains the aws_access_key_id and aws_secret_access_key.
If not, you may encounter the following error when pushing to Git:
error: GH013: Repository rule violations found for refs/heads/main.
