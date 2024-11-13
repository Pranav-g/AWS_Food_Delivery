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
