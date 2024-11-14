# AWS_Food_Delivery
Designing a AWS App using step functions and will add on features using event bridge

# Download the base stack file tree and AWS SAM configuration
cd ~/environment
wget -O ws-serverless-patterns.zip "https://ws-assets-prod-iad-r-iad-ed304a55c2ca1aee.s3.us-east-1.amazonaws.com/76bc5278-3f38-46e8-b306-f0bfda551f5a/module3/sam-python/ws-serverless-patterns-2024-04-30.zip"
unzip ws-serverless-patterns.zip
cd ws-serverless-patterns

sam build
sam deploy --guided --stack-name ws-serverless-patterns --capabilities CAPABILITY_IAM CAPABILITY_AUTO_EXPAND

# Install Python 3.9 if not installed
sudo apt-get update
sudo apt-get install python3.9
pyenv install 3.9.0   # Install Python 3.9 if using pyenv
pyenv global 3.9.0    # Set Python 3.9 as default


# Download and run the script
wget -O module3_setup.sh 'https://ws-assets-prod-iad-r-iad-ed304a55c2ca1aee.s3.us-east-1.amazonaws.com/76bc5278-3f38-46e8-b306-f0bfda551f5a/module3/sam-python/module3_setup-2024-04-30.sh'
chmod +x module3_setup.sh
source ./module3_setup.sh

export USERS_STACK_NAME=ws-serverless-patterns-users-1APGNJ7ZUC34
export ORDERS_STACK_NAME=ws-serverless-patterns-orders

# Install AWS
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
unzip aws-sam-cli-linux-x86_64.zip -d sam-installation
sudo ./sam-installation/install

# Check Stack output
aws cloudformation describe-stacks --stack-name $ORDERS_STACK_NAME --query "Stacks[0].Outputs"

#####
#####
# Delete
#####
####

export AWS_ACCESS_KEY_ID=""AKIAV6TLJWULEB554LFR export AWS_SECRET_ACCESS_KEY="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" export AWS_REGION="us-east-1"

# Run Python Test
pytest tests/integration -v

# Region
export AWS_DEFAULT_REGION=us-east-1

# Install Pytest
pip install pytest

# Launch py virtual env
python3 -m venv venv
source venv/bin/activate

# Install Boto3 in vertual env
pip install boto3





