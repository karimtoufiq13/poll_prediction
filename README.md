# poll_prediction
Democrat support over time with forecast 
Project Overview
This project demonstrates how to use bootstrapping techniques to estimate the mean and confidence intervals for polling data. The analysis is implemented in R and Python, leveraging both languages' powerful libraries for statistical computation and data manipulation.

Contents
poll_prediction.Rmd: The main R Markdown file containing the analysis code.
Data: The dataset used in this analysis is sourced from a public repository on GitHub.
Setup
Prerequisites
Ensure you have the following libraries installed:

R Packages
boot
reticulate
dplyr
Python Packages
pandas
Running the Analysis
Clone the repository:
bash
Copy code
git clone https://github.com/your-username/poll_prediction.git
Open the R Markdown file poll_prediction.Rmd in RStudio.
Ensure you have all the required packages installed. You can install the R packages using:
R
Copy code
install.packages(c("boot", "reticulate", "dplyr"))
Ensure you have Python installed with the necessary packages. You can install the Python packages using:
bash
Copy code
pip install pandas
Run the R Markdown file to execute the analysis and generate the HTML report.
Analysis Details
The analysis includes the following steps:

Setup: Loading necessary libraries and data.
r
Copy code
library(boot)
library(reticulate)
library(dplyr)
Data Loading: Loading polling data from a CSV file hosted on GitHub.
python
Copy code
import pandas as pd
polling = pd.read_csv("https://raw.githubusercontent.com/PriyaBrataSen/US-Election-Poll/main/pres_polls.csv")
Data Transformation: Converting the data to an R dataframe.
r
Copy code
df <- as.data.frame(py$polling)
Bootstrapping: Performing bootstrap resampling to estimate the mean and calculate confidence intervals.
r
Copy code
bootmean = function(x, i) { mean(x[i]) }
prefer_country = function(data) {
    results <- boot(data, bootmean, R = 1000)
    return(boot.ci(results, type = "perc"))
}
References
Bootstrapping Method to Estimate Voters Preferences in US Presidential Election 2020: Towards Data Science Article
Author
Karim Toufiq


Special Thanks to my Professor for showing me the ropes of R and Python! 
