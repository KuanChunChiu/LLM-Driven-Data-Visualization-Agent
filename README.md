# LLM Driven Data Visualization Agent

## Project Description
Datasets can often be complicated and messy, which are usually hard to interpret and understand before visualizing the numbers into diagrams. However, for non-technical users that don’t know about programming and visualization tools like Excel or Power BI, it can be difficult for them to visualize complex datasets. Therefore, the goal of this project is to create a LLM-based agent for data visualization purposes. Specifically, the agent is powered by the Qwen3-8B language model. The agent is capable of taking in a dataset and user request, generating plots from the dataset based on the request, and providing statistical information about the data with a brief summary for the plot generated. In this way, there’s no need for users to write code themselves, as they just need to provide their request and the dataset of interest, then leave all the work to the agent. 

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
After you run the project_qwen.py file, the first question you will see is "Are you exploring the electric vehicle dataset or flower dataset today? Enter 1 or 2 to indicate:". If you want to explore the EV dataset, then enter 1, or enter 2 if you're interested in the flower dataset. After indicating the dataset, you will be asked for your request with the kind of plot you want and what columns of the dataset are involved. Next, the agent will ask you the specific type of plot you want just to ensure it generates the right plot for you. After these three questions, you should see the line "Thanks, your request is received. I'm currently generating code to complete your request", which means the agent is now processing your request and you should be able to see the result is about 20 seconds.

Example:
If you're interested in the electric vehicle dataset and you want to know the relationship between cars' top speed and acceleration, then your user request should looks something like this:
- 1
- Give me a scatter plot showing the relationship between 'top_speed_kmh' and 'acceleration_0_100_s'
- Scatter plot

### Interpreting Agent Outputs:
The first half of the output consists of the agent written python code and the plot generated when that code is executed. The purpose of providing the code is for users to see what exactly is happening behind the hood and how the plot is generated. In this way, when the plot doesn't satisfy the request, users can check how the code is structured and copy it to do adjustment himself. The plot generated is right below the python code, and by default, it has a title, x-axis label, and y-axis label unless specified otherwise. Next, the second half of the output contains the statistical information about the numerical columns involved in the plot. Specifically, the stats include the columns's data count, mean, standard deviation, min, Q1, Q2, Q3, and max value. The second half output also contains a summary paragraph about the key pattern and trends found from the plot, which helps the users understand the insights from the data.

### Assessing Agent Performance:
To assess the agent's performance quality, run the evaluation_qwen.py file, which takes in 50 synthetic test cases from the test.py file and evaluate the agent's performance on those 50 tests. Each test case is a unique user request on one of the two csv datasets. The evaluation metrics employed to measure agent's performance are as follows:
- Generated code executes successfully
- Generated correct number of functions
- The function is named correctly
- Functions include the correct number of parameters
- No explanation, reasoning, or comments are embedded in generated code
- DataFrame variable is accessed with the correct name
- The relevant DataFrame columns are accessed
- Titles and x, y labels are included in the plot
- Factually correct statistics are provided

The eveluation result is returned as a dictionary containing the corresponding pass rate of each of the 9 metrics above, where the pass rate is the percentage of successful case out of the 50 test cases. This allows users to see agent's performance in data visualization and statistical summarization on not just one user request, but across 50 different requests involving different datasets and different type of plots. You are welcomed to add additional test cases to your local test.py file to further assess the agent's functionality.

## Analysis You Can Do Using This Agent
- What's the relationship between vehicle's efficiency in watt-hours per km and range in km?
- What's the average vehicle battery capacity for each battery type?
- What's the distribution of flower's petla width in cm?
- What does the frequency heat map of flower's sepal length and sepal width look like?
- Is the Qwen3-8B model better at calculating the dataset statistics or writing errorless code?

## Contributors
1. Kuan-Chun Chiu (Myself) - beagledirk1@gmail.com
2. Karl Thilking - thilking.k@northeastern.edu
