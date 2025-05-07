# Regression model: Coffee Shop Sales ☕
A project using Azure Machine Learning to predict sales, improve profit, stock management and reduce losses.

### The aim of this project is to consolidate and utilize explored concepts and Knowledge in order to build a real, practical project in Machine Learning.

The process includes collecting and preparing data, selecting suitable machine learning algorithms (such as regression or supervised learning methods), and training the model. After training, the model is evaluated using performance metrics and then deployed to generate real-time predictions. Data analytics tools, machine learning frameworks, and cloud deployment services are used to ensure that the solution is scalable and efficient. As such, the Technical Goals are:

#### ✅ Train a Machine Learning model to predict sales based on the temperature of the day.
#### ✅ Register and manage the model using MLflow.
#### ✅ Deploy the model for real-time predictions in a Cloud Computing environment, using Microsoft Azure.
#### ✅ Create a structured pipeline to ensure reproducibility and facilitate maintenance by the entire team involved.

# Business Context 💡
Café Aurora is a local coffee shop that experiences fluctuations in sales depending on the weather, especially temperature. On colder days, hot drinks are in higher demand, while on warmer days, iced beverages and foot traffic vary significantly.

Local coffee shops rely heavily on daily demand:

#### They work with perishable products (milk, sweets, ground grains).

#### A large part of the production is done on the same day, requiring demand forecasting.

Based on the observation that the amount of coffee sold daily has a strong correlation with the ambient temperature, the coffee shop owners decided to look for a way to predict how much will be sold, in order to plan accordingly. They gathered data on 100 days, listing the ammount of coffee sold, and the temperature on said day, and compiled it all into a .csv file.

The goal is to build a simple yet effective predictive model that estimates how many coffees will be sold on a given day, based on the forecasted temperature. This enables better preparation and decision-making.

| Benefit                           | Impact                                                                            |
| --------------------------------- | -------------------------------------------------------------------------------------------- |
| **Smarter inventory planning**    | Reduce waste by preparing the right amount of fresh ingredients (milk, fruits, bakery items) |
| **Optimized staffing**            | Avoid overstaffing or understaffing by predicting busy days                                  |
| **Efficient product preparation** | Prepare drinks and pastries in advance based on expected demand                              |
| **Weather-based promotions**      | Trigger automated discounts or ads (e.g., iced coffee discounts on hot days)                 |
| **Higher profit margins**         | Lower losses from unsold stock and improve resource utilization                              |
| **Improved customer experience**  | Shorter wait times, better service, and fewer stockouts                                      |

# Dataset Utilized 📊
The following dataset was used, containing 100 lines in total, and was made using ChatGPT. You can find the CSV file in the inputs folder.

# Starting the Project 🔧
## 1. Creating a resource group and naming It.
![image](https://github.com/user-attachments/assets/48742988-02aa-4fc3-8a4a-e02414c557df)
## 2. Create the AzureML Workspace
![image](https://github.com/user-attachments/assets/3b9acefe-aab8-407e-b578-8e044d185882)

# Inside the Azure Machine Learning Studio 🧰
## 1. Create a compute instance
A compute instance is a fully managed cloud-based workstation optimized for your machine learning development environment. I'll be doing all the testing with Jupyter Notebook with it.
Also note that since i am using an Azure for Students subscription, it's important to choose a low-cost alternative, in order to save as much as possible.
![image](https://github.com/user-attachments/assets/d60c5307-4da8-4aea-a117-0371b8554e9d)
## 2. Create a compute cluster
Unlike the compute instance, clusters are better suited to actually do the Model training. You have to keep the costs in mind here as well.
![image](https://github.com/user-attachments/assets/285e27d3-ba96-43c6-8521-941b418c733b)
## 3. Add the .csv file as a data asset
![image](https://github.com/user-attachments/assets/fbc42b56-cc92-4979-a48a-18c2c9638f18)

# Making an Experiment with a Notebook 🧾
Notebooks in Azure Machine Learning are cloud-hosted Jupyter environments built into Azure ML Studio. They allow you to:

Write and execute Python code for data exploration, model training, and evaluation.

Work with cloud-based compute instances without setting up local environments.

And more!

So i got to making some code in order to experiment with the Dataset and MlFlow before making any models using AutoMl or Designer.
In order to do that, i uploaded these Files 📁

- `coffee_sales_experiment.ipynb` – The main notebook containing all the steps, fully annotated.
- `coffee_sales_data.csv` – The dataset with 100 rows of synthetic data (temperature vs. coffee sales).

This is the Code i used for the Experiment:

![image](https://github.com/user-attachments/assets/7c150cd7-05d3-4bef-9d2e-6f1c647469d9)

And this is the Job created by running it:

![image](https://github.com/user-attachments/assets/314cf251-4eb7-4272-978c-4d71dc4dbaf4)


# The Different ways to create a model 📈
## 1. Using AutoML 
Automated Machine Learning (AutoML) is a process that automates the selection, training, and tuning of machine learning models. Instead of manually choosing algorithms and tweaking hyperparameters, AutoML tests multiple combinations to find the best-performing model for a given dataset.

![image](https://github.com/user-attachments/assets/a8f3fc48-501f-49cc-aae6-5fce4035e02d)

Also, since this is supposed to be a first experiment, i also blocked most of the Models it should use during training so that it loaded faster.

![image](https://github.com/user-attachments/assets/9aff1d33-a130-49a8-b556-d147893df652)

## 2. Using Designer
Azure Machine Learning Designer is a drag-and-drop interface that lets you build, train, and deploy machine learning models without writing code. It’s a visual environment ideal for both beginners and professionals who want to quickly prototype models or teach ML concepts.

![image](https://github.com/user-attachments/assets/be9de3a5-a53e-4082-99d3-3e66e40942ef)

In this project, I replicated the same logic used in the AutoML experiment, but using a more manual and visual approach with the Designer.

Pipeline Overview:

##### Dataset import and selection: The dataset containing coffee sales and temperature data was loaded and filtered for relevant columns.

##### Data split: The dataset was split into training and testing sets (in this case, 80/20).

##### Model training: A Linear Regression model was selected and trained using the training subset.

##### Scoring and evaluation: The model was then scored on the test data and evaluated using regression metrics (like R² and RMSE).

# The Metrics and Results from the chosen Model 📌

## 1. Metrics:

![image](https://github.com/user-attachments/assets/b8ffe85d-5cfb-4dfc-aea8-46f1b0154c8e)


## 2. Results:

![image](https://github.com/user-attachments/assets/450acdac-337b-4db5-8be8-207eabb77518)


# Conclusion:
After choosing which model to use, you need only to deploy it!
With this, you can utilize these models to predict future sales and plan accordingly!
in summary, it's a great way to put to practice the theory of working with AzureML.
