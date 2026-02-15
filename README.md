# LLM Driven Data Visualization Agent

## Project Description
Datasets can often be complicated and messy, which are usually hard to interpret and understand before visualizing the numbers into diagrams. However, for non-technical users that don’t know about programming and visualization tools like Excel or Power BI, it can be difficult for them to visualize complex datasets. Therefore, the goal of this project is to create a LLM-based agent for data visualization purposes. The agent should be capable of taking in a dataset and user request, generating plots from the dataset based on the request, and providing statistical information about the data with a brief summary for the plot generated. In this way, there’s no need for users to write code themselves, as they just need to provide their request and the dataset of interest, then leave all the work to the agent. 

## Example Agent Use
User prompting requests

![User Request](https://github.com/user-attachments/assets/0bf72707-c27f-4ff9-90c6-10d3e06d0d56)

Agent generates the requested plot

![Plot Generation](https://github.com/user-attachments/assets/fa701bf8-f136-41e5-8c5f-7b664ef21ee8)

Agent generates statistics info and summary of the plot

![Statistics & Summary](https://github.com/user-attachments/assets/0227a24d-b1f4-4674-af6d-b8dd1cb8d56a)

## How to Install and Use the Agent
### Dependencies:
  - transformers >= 4.56.2
  - matplotlib >= 3.10.6
  - seaborn >= 0.13.2
  - pandas >= 2.3.2
  - numpy >= 2.3.2
  - torch >= 2.8.0
  - ast >= 3.12.10
  - re >= 3.12.10

### Instructions:
  1. Make sure all libraries in the above dependency list are installed to your current working environment, and the versions are all up to date
  2. Download the three py files from home and two csv files from the Data folder. The csv files contains the datasets while the py files contain the python code that powers the agent
  3. Run the project_qwen.py file and the agent will start running. Follow the prompt and enter your request to get the desired plot and statistics from one of the two datasets
  4. To assess the accuracy and quality of Agent, run the evaluation_qwen.py file to get the average pass rate of 9 performance metrics across 50 synthetic test cases

### Troubleshooting:
  - If there's error reading the csv files, make sure they're in the Data folder in your current working directory, and their names aren't modified after downloaded
  - If there's error with the libraries used, make sure they're all properly installed to your current environment, and the version are the same or newer than the versions in the dependency list
  - If there's error with running the agent, make sure you specify the correct csv dataset to work with and provide a clear prompt and plot type to receive. If necessary, download the py files again or restart        your computer before running the file again

## How to Use the Agent
### Prompting User Request:


### Interpreting Agent Outputs:


### Assessing Agent Performance:


## Analysis You Can Do Using This Agent
- 
- 
- 
- 
- 

## Contributors
1. Kuan-Chun Chiu (Myself) - beagledirk1@gmail.com
2. Karl Thilking - thilking.k@northeastern.edu
