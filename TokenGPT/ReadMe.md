# Project: TokenGPT - Your AI Assistant for Blockchain Research and Development
## Introduction

TokenGPT is an innovative AI assistant designed to streamline and enhance blockchain research and development processes. By leveraging the power of advanced language models, TokenGPT provides real-time assistance, code generation, and insightful analysis, making it an invaluable tool for blockchain developers and researchers.

## Key Features of TokenGPT:

Code Generation: Generate high-quality, efficient, and secure blockchain code snippets.

Code Explanation: Understand and explain complex blockchain code, making it easier to learn and debug.

Research Assistance: Access a vast knowledge base of blockchain research papers and technical documentation.

Natural Language Queries: Interact with the AI assistant using natural language queries, making it accessible to users of all technical backgrounds.

Real-time Feedback: Receive immediate feedback and suggestions on your blockchain projects.

## How to Use TokenGPT:

Prepare Your Development Environment:
Ensure you have the necessary tools and libraries installed, such as Python, a suitable IDE, and blockchain development frameworks like Ethereum, Solana, or others.

Integrate TokenGPT:
Use TokenGPT's API or SDK to integrate the AI assistant into your development workflow.

Interact with TokenGPT through a command-line interface, a web-based interface, or directly within your IDE.
By utilizing TokenGPT, you can significantly accelerate your blockchain development process, improve code quality, and gain deeper insights into the complex world of blockchain technology.

# Implementation 

## Step 1: Set Up Ubuntu Environment
### Option 1:
To set up Ubuntu on VMware reference the steps taken in the video
 https://youtu.be/SgfrHKg81Qc?si=_QFQQTA_jlb4UDiu
### Option 2: 
To set up Ubuntu environment on your device follow the steps taken in 
Windows 11 : https://www.youtube.com/watch?v=Uh9643c2P6k
Mac: https://youtu.be/1WWj6qoWhJw?si=2fcx_KeyETraPzOX

## Step 2: Prepare the Development Environment 
```
Install Python
Install pip
```
Set up a Virtual Environment
#### 1.	Check if Python is already installed:
Open a terminal window (search for "Terminal" in your applications menu).
Type the following command and press Enter:
```
python3 --version
```
•	If the command displays the Python version information (e.g., Python 3.x.x), then Python is already installed.
•	If the command returns an error message like "command not found," Python is not installed.
#### 2.	Install Python if needed (using Ubuntu as an example):
If you need to install Python, follow these steps (specific instructions might differ slightly for other operating systems):
•	Visit this guide for detailed instructions on installing Python on Ubuntu: https://www.makeuseof.com/install-python-ubuntu/
#### 3.	Verify Python installation (after installation):
Once you (potentially) installed Python, return to the terminal window and run the following command again:
```
$python3 –version
$sudo apt upgrade
```

![image](https://github.com/user-attachments/assets/8b963275-56cb-48bc-940b-fed0963c41a9)


This should now display the installed Python version information.
Install pip 
```
$sudo apt update 
$sudo apt install python3-pip
```

![image](https://github.com/user-attachments/assets/28551087-a213-49ee-8661-c8c27417772a)



### 1. Install Virtualenvwrapper: 
Use the package manager to install the necessary tools: 
```
$sudo apt install virtualenv virtualenvwrapper
```
 
Configure Bash: 
Open your .bashrc file: 
```
$nano ~/.bashrc
```
Add the following lines to the end of the file: 
```
# Virtualenvwrapper configuration
export WORKON_HOME=$HOME/.virtualenvs
export PROJECT_HOME=$HOME/projects
source /usr/local/bin/virtualenvwrapper.sh
```
Save and close the file.
Source the changes: 

```
$source ~/.bashrc
```

![image](https://github.com/user-attachments/assets/752c0dd1-46c4-43bb-9659-e39020011c1d)


## Test virtual environment 
```
$mkvirtualenv CS572
``` 
Get OpenAI API keys Sign up an account: https://openai.com/product and create a new secret key under API Keys menu item
 
![image](https://github.com/user-attachments/assets/2683034c-2544-4def-b12f-c624591e3c2d)


![image](https://github.com/user-attachments/assets/e6a9f0a1-a760-4a09-9325-4c6bdb94f863)


Save your key by copying as you will use it in setting up the connection



## Install Python openai 
``` 
$workon CS572 
$pip install openai
```

![image](https://github.com/user-attachments/assets/803a23c4-1173-45d2-9a11-e8ae529ab90f)

Test API keys Create .env file nano .env
```
API_KEY=Paste_the_API_key_you_copied_from_the_OpenAI_site_here 
```

Find your Organization ID: You'll need to reference the OpenAI API documentation for authentication details, which can be found at this link: https://platform.openai.com/docs/api-reference/authentication

Set your environment variables: This line (source .env) assumes you have a file named .env that stores your API key and potentially your organization ID. 
Run the curl command: 
•	This command (curl https://api.openai.com/v1/models...) checks if you can access information about available models on the OpenAI platform.
•	It includes two headers: 
o	Authorization: Bearer $API_KEY - This header tells the API to use your API key for authentication. You'll need to replace $API_KEY with your actual API key retrieved from OpenAI.

 
Create test_env.py 
```
import os 
import openai
def init_api():
test-env.py
with open('.env') as env:
for line in env:
key, value = line.strip().split('=') os.environ[key] = value
openai.api_key = os.environ.get('API_KEY') openai.organization = os.environ.get('ORG_ID')
init_api()
models openai.Model.list()
print('Models:')
print(models)
```

You can view your file with 
```
$python3 test-env.py
```
And you will see something like this.

![image](https://github.com/user-attachments/assets/7eef1312-065a-48ea-adfb-852dff7c3f0e)




