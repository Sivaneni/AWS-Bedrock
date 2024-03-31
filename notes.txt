conda create -p venv python==3.10 -y
conda activate venv/
//configure IAM in AWS console and also see requirments.txt file where we installed boto3,awscli(pip install -r .\requirements.txt)
aws configure

****provide access-keyid and secret-access key,region,output  format
grant access to all models that you want and then we can create a simple code

please check below sample code files
1.llama2.py
2.stablediffusion.py

you can run from your environemnt simply by 
python .\stablediffusion.py

to comeout of environment
conda deactivate

conda env remove --name venv


# to delete a access key for a particular IAM user
aws iam delete-access-key --user-name <user-name> --access-key-id <access-key-id>


#Before pushing the code to git make sure \.aws\credentials file contains aws_access_key_id,aws_secret_access_key if not you will get below error

error: GH013: Repository rule violations found for refs/heads/main.
