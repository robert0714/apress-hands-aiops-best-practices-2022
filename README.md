# AIOps
## Environment Setup
You have three options to set up an environment.
* [Use Python](https://www.python.org/downloads/) 
* [Use Anaconda](https://www.anaconda.com/distribution/)
* Use cloud services
### Use cloud services
This is the simplest of all the options but needs Internet connectivity to use. Cloud providers such as Microsoft Azure Notebooks and Google Collaboratory are popular and available at the following links:

* Microsoft Azure Notebooks: https://notebooks.azure.com/
* Google Collaboratory: https://colab.research.google.com

### Use Anaconda
Anaconda is a Python distribution and made for large data processing, predictive analytics, and scientific computing requirements. The Anaconda distribution is the easiest way to perform Python coding, and it works on Linux, Windows, and macOS.

* [Installation]()
  * [Verifying your installation](https://docs.anaconda.com/anaconda/install/verify-install/)
* [Managing environments](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html)

# Chapter 6 AIOps Use Case: Deduplication
* Open cmd:
```
git clone https://github.com/robert0714/apress-hands-aiops-best-practices-2022
cd  apress-hands-aiops-best-practices-2022
jupyter notebook Ch-6_Deduplication.ipynb
```
* You can modify the file: `Ch-6_Deduplication.ipynb`
    ```python
    df_dedup[:10].plot(kind="bar", by="Count", x="Host")
    # df_dedup adjust to the below..
    df_dedup[:10].plot.bar(  y="Count", x="Host"  );    
    # df_dedup
    ```
# Chapter 7  AIOps Use Case: Automated Baselining
## Implementation of ARIMA and SARIMA
* https://www.kaggle.com/code/sadeght/arima-sarima-simple-clear-analysis
* https://www.kaggle.com/code/prakharprasad/time-series-iii-arima-sarima
### Creating sample data
* Using shell to collect.
```shell
apt install -y sysstat
pidstat 
pidstat | grep 207 | awk '{ print $1, $8 }' >> cpu_utilization-data.csv
pidstat -p 207 1
Linux 5.15.89+ (cs-882156113206-default)        03/25/23        _x86_64_        (4 CPU)

09:57:48      UID       PID    %usr %system  %guest   %wait    %CPU   CPU  Command
09:57:49        0       207    0.00    0.00    0.00    0.00    0.00     2  dockerd
09:57:50        0       207    0.00    0.00    0.00    0.00    0.00     2  dockerd
09:57:51        0       207    0.00    0.00    0.00    0.00    0.00     2  dockerd
09:57:52        0       207    0.00    0.00    0.00    0.00    0.00     2  dockerd
```
* Using chatGPT to get data
Using browser to website :https://chat.openai.com/chat .
Using the below prompt:

```shell
Give me an example with daily data points for a full year from 2022/07/14, with two columns, date_time and cpu_utilization (multiplied by 100)  in CSV format !
```
### Using Others
* https://github.com/amcs1729/Predicting-cloud-CPU-usage-on-Azure-data
* https://gist.github.com/fornasari12/ece7fa5f46c62a8c68db657ba96ca438
* https://www.kaggle.com/datasets/boltzmannbrain/nab?select=README.md
* https://www.projectpro.io/article/how-to-build-arima-model-in-python/544