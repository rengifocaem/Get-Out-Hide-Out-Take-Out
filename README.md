# Get-Out-Hide-Out-Take-Out

Exploration of Gun Violence in the USA utilizing multiple datasets from different sources. Gun Violence data, Gun Laws data, School System data and U.S. Opiate Prescriptions/Overdoses data are explored using python 3.6.

## Summary & Insights

### Inspiration

The title of this repository "Get-Out-Hide-Out-Take-Out" gives you an idea of the inspiration for this work. Nowadays, it is not uncommon to have to think of a plan in case of an active shooter. By taking a look at the gun violence data, it is our hope to better educate ourselves and others about common questions about this horrific incidents.

### Which states have the most gun violence incidents?

Using the Gun Violence dataset, we compared the US states by adding up all the deaths and injuries for each state (for the time frame data was collected). Our findings seemed biased towards the more populated states, so we plotted these numbers on a per million people basis. The results show that when looking at the deaths and injuries on a per million basis, California, Texas, Florida, Illinois and Ohio are NO longer at the top 5 for either deaths or injuries, and shows the District of Columbia is the most violent place per both metrics, deaths and injuries per million people.

![Image of US Gun Violence Top 15 States 2013 to 2018 data Both](https://github.com/Leo8216/Get-Out-Hide-Out-Take-Out/blob/master/images/US_Gun_Violence_Top_15_States_2013-2018_data_pM.png)

### Which are the worst incidents of gun violence in recent history and where did they happen? 

The Gun Violence dataset provided location data by longitude and latitude for each violent act. The visual below shows the top 50 violent acts that where most impactful, measuring impact as the sum of people killed and people injured. Notice only one of the top 50 violent acts happened in the North-West. As a note for the reader, the data does not include the unfortunate incident that happened in October 2017 in Las Vegas Nevada.

![Image of Location_of_top_50_impactful acts](https://github.com/Leo8216/Get-Out-Hide-Out-Take-Out/blob/master/images/Location_of_top_50_impactful_acts.png)

### Do states with the higher number of restrictive laws have less gun violence?

To answer this, we estimated the number of restrictive and permissive gun laws per state from the US gun laws dataset, and plotted it next to the total killed per million people in the state. The District of Columbia (most killed per million people) only has 1 permissive law vs 13 restrictive laws. On the other hand, California, the state with the most restrictive laws (27 per this dataset) and only 2 permissive ones, does not rank in the bottom 25%. This could mean restrictive laws are not necessarily impacting gun violence as many expect them to.

![Image of Gun_Kills_vs_Gun_Laws](https://github.com/Leo8216/Get-Out-Hide-Out-Take-Out/blob/master/images/Gun_Kills_vs_Gun_Laws.PNG)

### Is there a correlation between education quality and gun violence?

From the US school systems data, we obtained education performance score for states school systems, and plotted it versus the number of killed per million people in the state. There seems to be a correlation between them. Notice that when performance ranking > 60%, the # of people killed is less than 200 per million people in the state. This might open the debate about government focusing on education (schools) more than in correction (prisons)?

![Image of State_Education_vs_State_Gun_Violence](https://github.com/Leo8216/Get-Out-Hide-Out-Take-Out/blob/master/images/State_Education_vs_State_Gun_Violence.png)

## Required Imports
This was run in Python 3.6
```
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
% matplotlib inline
import plotly
import plotly.graph_objs as go
from datetime import date
from plotly.offline import init_notebook_mode, iplot
import plotly.plotly as py
from plotly import tools
import string, os, random
import calendar
init_notebook_mode(connected=True)
punc = string.punctuation
from datetime import datetime
from PIL import Image
from wordcloud import WordCloud # wordcloud needs to be installed in your machine
```

## Datasets
* **US Gun Violence Data** [link to Kaggle dataset.](https://www.kaggle.com/jameslko/gun-violence-data) The CSV file contains data for all recorded gun violence incidents in the US between January 2013 and March 2018, inclusive.
* **US State Population Data** [link to U.S. Census Bureau.](https://www.census.gov/data/datasets/2017/demo/popest/state-total.html) Annual Estimates of the Resident Population for the United States, Regions, States, and Puerto Rico: April 1, 2010 to July 1, 2017
* **US Gun Law Data** [link to RAND State Firearm Law Database.](https://www.rand.org/pubs/tools/TL283.html)  A longitudinal data set of state firearm laws that is free to the public, including other researchers, to support improved analysis and understanding of the effects of various laws. 
* **US State School System Data** [link to Wallethub.](https://wallethub.com/edu/states-with-the-best-schools/5335/) To determine the top-performing school systems in America, WalletHub’s analysts compared the 50 states and the District of Columbia across 21 key measures.
* **US Opiates Overdoses Data** [link to Kaggle dataset.](https://www.kaggle.com/apryor6/us-opiate-prescriptions) Contains information on opioid related drug overdose fatalities.

## Authors

* **Leo Barbosa**
* **Carlos Rengifo**
