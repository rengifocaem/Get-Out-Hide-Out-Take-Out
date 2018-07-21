# Get-Out-Hide-Out-Take-Out
Exploration of Gun Violence in the USA utilizing multiple datasets from different sources. Gun Vilolence data, Gun Laws data and School System data are explored using python.
Summary & Insights
Inspiration
The title of this repository "Get-Out-Hide-Out-Take-Out" gives you an idea of the inspiration of this work. Nowdays, is not uncommon to talk about what to do in case of an active shooter. This is something many years ago would not cross people's minds. So, we wanted to take a look at the gun violence data and provide meaningful insights to help people answer questions they may be wondering about such as "which of these States is less violent?" or "waht places are more likely to have gun violence".

Which states have the most gun violence incidents?
From the Gun Violence dataset, we were able to compare all the states by adding up all the deaths and injuries for each state (for the time frame data was collected), and sorting from largest to smallest. Our findings seemed biased towards the more populated states, so we plotted these numbers on a per million people basis. The results show that when looking at the deaths and injuries on a per million basis, California, Texas, Florida, Illinois and Ohio are NO longer at the top 5 for either deaths or injuries, and shows the District of Columbia is the most violent state per both metrics, deaths and injuries per million people in the state.

Image of US Gun Violence Top 15 States 2013 to 2018 data Both

Which locations are more prone to have a gun violence incident?
This one was easy: WordCloud. The image below was generated from the top 50 gun violence incidents locations. Many of which we expected to see such as "Bar" and "Motel". One odd one was "Intl Airport", but we were most shocked to see that "Elementary", "Middle" and "High school" show up in the top 50.

Image of Crime_Location_WordCloud

Do states with the higher number of restrictive laws have less gun violence?
To answer this, we estimated the number of restrictive and permissive gun laws per state from the US gun laws dataset (see details for all datasets used under the dataset section), and plotted it next to the killed per million by state. The distrcit of Columbia (most killed per Million People) only has 1 permissive law vs 13 restrictive laws. On the other hand, California, the state with the most restrctive laws (27 per this dataset, and only 2 permissive ones) does not rank in the bottom 25%. This could mean restrictive laws are not necessarily impacting gun violence as many expect tehm to.

Image of Gun_Kills_vs_Gun_Laws

Is there a correlation between education quality and gun violence?
From the US school systems data, we obtained a ranking score for overall performance of states school systems, and plotted it vs the number of Killed per Million people in the state. There seems to be a correlation between them. The state with The result show that when performance ranking > 60%, the # of people killed is less than 200 per million people in the state. Maybe we should focus on bringing performance rank for all school systems above 60%, would that lead to a massive decrease of gun violence?

Image of State_Education_vs_State_Gun_Violence

Required Imports
This was run in Python 3.6

import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
% matplotlib inline

import plotly
import plotly.graph_objs as go

# wordcloud needs to be installed in your machine  
from PIL import Image
from wordcloud import WordCloud
Datasets
US Gun Violence Data link to Kaggle dataset. The CSV file contains data for all recorded gun violence incidents in the US between January 2013 and March 2018, inclusive.
US State Population Data link to U.S. Census Bureau. Annual Estimates of the Resident Population for the United States, Regions, States, and Puerto Rico: April 1, 2010 to July 1, 2017
US Gun Law Data link to RAND State Firearm Law Database. A longitudinal data set of state firearm laws that is free to the public, including other researchers, to support improved analysis and understanding of the effects of various laws.
US State School System Data link to Wallethub. To determine the top-performing school systems in America, WalletHub’s analysts compared the 50 states and the District of Columbia across 21 key measures.
Authors
Leo Barbosa
Carlos Rengifo
