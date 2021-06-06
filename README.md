<h1>Anomaly-Detection-in-Bitcoin-Transactions</h1>

<h3>Abstract</h3> 
<p>Bitcoin has become a preferred method for transferring money for illicit economicactivity such as ransomware payments and money laundering. Robust detectionof these illicit transactions in the Bitcoin blockchain is crucial for anti-moneylaundering operations.  Major challenges for illicit transaction detection includethe lack of transaction labels, the massive size of the bitcoin network, and thefact the bad actors work to mask their activity and avoid detection.   Previousresearchers have proposed anomaly detection methods, supervised learning, andactive learning to classify illicit transactions. Supervised learning is necessary toclassify illicit transactions as illicit transactions do not correlate with anomaliesin the dataset. Unsupervised learning methods are useful when there’s scarcity oflabels.  Active learning is a useful modification of supervised learning for illicittransaction classification as real world bitcoin datasets have very few licit/illicitlabels. We compare the performance of these methods using the Elliptic dataset.</p>

<h3>Data Source</h3>
<p>We use the Elliptic Data Set which contains 200K Bitcoin transactions, a subset of which are tagged as belonging to either licit or illicit categories. This dataset is a time series graph where Bitcoin transactions are nodes in the network and directed payment flows are edges. Along with licit or illicit tags, the nodes are also tagged with 166 additional node features. 94 of the features are local information about the transaction, such as the time step, transaction fee, and output volume. 72 features are aggregated features which are aggregated information from the nodes one-hop backward and forward. The data is divided evenly into 49 time steps. In each time step, the transactions are connected as a single component. There is an important event occurs at time step 43 which is a sudden closure of a dark market. This causes the number of illicit data to decrease significantly after the shut down.</p>

<p>We use this dataset to evaluate the effectiveness of anomaly detection methods to classify illicit transactions, reproduce supervised learning classification method employed in previous studies, including AL, and evaluate the performance of a modification to the AL method that uses the network graph to aid in selecting datapoints.</p>

<h4> Links to Data set and Data dictionary</h4>
<ul><li>The datasets are available for public use under <a href='https://www.census.gov/programs-surveys/household-pulse-survey/datasets.html'>census.gov</a> website as weekly files.</li>
<li>Data dictionary is available in the census.gov website under the link <a href='https://www.census.gov/programs-surveys/household-pulse-survey/technical-documentation.html#phase1'>Phase 1 Household Pulse Survey Technical Documentation.</a> It has also been added to the repository. Please refer to repository structure for pulse2020_data_dictionary.xlsx</li></ul>

<h4>Download data</h4>
<p>Data is directly downloaded from census website using python modules. Refer to the data_cleaning.ipynb for detailed downloading steps<p>
  
<h4>Terms of use of census data </h4>
<p>The Census Bureau is committed to open government by sharing its public data as open data. Census data continues to be a key national resource, serving as a fuel for entrepreneurship and innovation, scientific discovery, and commercial activity.  We continuously identify and publish datasets and Application Programming Interface’s (API’s) to Data.gov in accordance with the Office of Management and Budget (OMB) Memorandum M-10-06, the Executive Order 13642 on open data, and the overall principles outlined in the Digital Government Strategy.  In
 accordance with the Open Data Policy, M-13-13, the Census Bureau publishes its information in machine-readable formats while also safeguarding privacy and security.</p>

<h3>Repository structure</h3>

```
├── README.md
├── LICENSE
├── data
├── images
├── notebooks
```
<h3>How to run the notebook</h3>

<li>Install Anaconda</li>
<li>Using a terminal or cmd, navigate to the src folder.</li>
<li>Launch jupyter by running: jupyter notebook</li>
<li>Select the notebook of interest. (Start at data_cleaning.ipynb for the full process or analysis.ipynb for the final report.)</li>

<h3>Resources used</h3>

This analysis was prepared using Python 3.8 running in a Jupyter Notebook environment.  
Documentation for Python can be found here: https://docs.python.org/3.8/  
Documentation for Jupyter Notebook can be found here: http://jupyter-notebook.readthedocs.io/en/latest/  

The following Python packages were used and their documentation can be found at the accompanying links:

* [pandas](https://pandas.pydata.org/)
* [numpy](https://numpy.org/)
* [IPython](https://ipython.org/)
* [matplotlib](https://matplotlib.org/)
* [seaborn](https://seaborn.pydata.org/)
