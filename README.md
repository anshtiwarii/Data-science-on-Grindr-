## UNSTRUCTURED DATA ANALYSIS

```
ANALYSIS BY -
```
```
Raloue R Kapoor
Akshiti Parashar
Ansh Tiwari
Srihari Ananthan
```

# INDEX

1. Introduction
    a. Understanding the Data
2. Data Cleaning
    a. How did we prepare it for training?
b. Data count vs Country
c. Correlation heatmap
3. Anomaly Detection
    a. Applying LOF and HBOS
b. Understanding the results
4. Performing EDA
    a. EDA Plots
b. Deriving conclusions


### Intro: What’s Unstructured data?

Unsupervised or undirected data science uncovers hidden patterns in
unlabeled data. In unsupervised data science, there are no output variables
to predict.

### How to work about it?

We use Unsupervised Methods. These methods also estimate that any
malicious data would be different statistically from normal data.

Here, we have performed both HBOS and LOF for a comparative analysis.


### DATA CLEANING
###### How did we prepare it for training?
1. Filtered columns like GEO_AS_(#), GEO_CITY_(#), GEO_LAT_(#), the time
    columns, etc. by combining/combining them for columns with useful
    values. Eg. Eliminated the city, country, region, etc. based on if it matches
    with IP address, latitude and longitude.
2. Divided motion and orientation columns into 3 parts (x, y, z).
3. Added isMotionTrue and difference_time columns.
4. Extracted columns for Android version and Phone model from
    appVersion column.
5. Eliminated the redundant columns.
6. Categorized the remaining columns into Features and TVs.
7. Eliminated rows with >10 NaN values.






![](https://github.com/anshtiwarii/Unstructured-Data-Analysis/blob/master/Plots/UNSTRUCTURED%20DATA.png)

As you can see, the peaks on the graph show that Most of our data is from Countries like Brazil, India, Taiwan etc which means that we can expect more bad bots from these states, as will be explained ahead

![](https://github.com/anshtiwarii/Unstructured-Data-Analysis/blob/master/Plots/UNSTRUCTURED%20DATA%20(1).png)
The graph on the left tells us the magnitude of correlation between the features, while the right graph is the standard plot. According to this graph, we removed the features that had low correlation.

![](https://github.com/anshtiwarii/Unstructured-Data-Analysis/blob/master/Plots/UNSTRUCTURED%20DATA%20(2).png)


![](https://github.com/anshtiwarii/Unstructured-Data-Analysis/blob/master/Plots/UNSTRUCTURED%20DATA%20(3).png)

### Performing EDA

We started to plot data by taking different columns together and tried to come
up with a good insight from it. These are the few plots we drew -

1. Heatmap of Day of the Week vs Hour of the day
2. Provider vs Memory
3. Android Version vs Providers
4. Android version vs Labels
5. Service Provider vs Labels
6. Plotting outliers on map
7. Analyzing features ,TV with outliers to obtain visual and workable results




![](https://github.com/anshtiwarii/Unstructured-Data-Analysis/blob/master/Plots/UNSTRUCTURED%20DATA%20(4).png)



![](https://github.com/anshtiwarii/Unstructured-Data-Analysis/blob/master/Plots/UNSTRUCTURED%20DATA%20(5).png)



![](https://github.com/anshtiwarii/Unstructured-Data-Analysis/blob/master/Plots/UNSTRUCTURED%20DATA%20(6).png)



![](https://github.com/anshtiwarii/Unstructured-Data-Analysis/blob/master/Plots/UNSTRUCTURED%20DATA%20(7).png)



![](https://github.com/anshtiwarii/Unstructured-Data-Analysis/blob/master/Plots/UNSTRUCTURED%20DATA%20(8).png)



![](https://github.com/anshtiwarii/Unstructured-Data-Analysis/blob/master/Plots/UNSTRUCTURED%20DATA%20(9).png)



![](https://github.com/anshtiwarii/Unstructured-Data-Analysis/blob/master/Plots/UNSTRUCTURED%20DATA%20(10).png)



![](https://github.com/anshtiwarii/Unstructured-Data-Analysis/blob/master/Plots/UNSTRUCTURED%20DATA%20(11).png)



![](https://github.com/anshtiwarii/Unstructured-Data-Analysis/blob/master/Plots/UNSTRUCTURED%20DATA%20(12).png)



![](https://github.com/anshtiwarii/Unstructured-Data-Analysis/blob/master/Plots/UNSTRUCTURED%20DATA%20(13).png)



![](https://github.com/anshtiwarii/Unstructured-Data-Analysis/blob/master/Plots/UNSTRUCTURED%20DATA%20(14).png)



![](https://github.com/anshtiwarii/Unstructured-Data-Analysis/blob/master/Plots/UNSTRUCTURED%20DATA%20(15).png)



![](https://github.com/anshtiwarii/Unstructured-Data-Analysis/blob/master/Plots/UNSTRUCTURED%20DATA%20(16).png)



![](https://github.com/anshtiwarii/Unstructured-Data-Analysis/blob/master/Plots/UNSTRUCTURED%20DATA%20(17).png)



### Bad bots vs good bots

```
● Bots are autonomous programs on a network (especially the Internet) which can interact with
systems or users.
● Some Bots are especially designed to behave like a person on the network.
● A good bot is any bot that performs useful or helpful tasks that aren't detrimental to a
user's experience on the Internet.
● Bad bots scrape data from sites without permission in order to reuse it (e.g., pricing,
inventory levels) and gain a competitive edge. The truly nefarious ones undertake criminal
activities, such as fraud and outright theft.
● Because good bots can share similar characteristics with malicious bots, the challenge is
ensuring good bots aren't blocked when putting together a bot management strategy.
● Bad bots generally spend more time, and occupy more memory on the site and servers.
● With enough data one can differentiate between good and bad bots.
```

### Finding bad bots / fake users

**1. Set duration of ad threshold to 60% of max duration (0.12 seconds)
2. Set memory used to threshold of 60% of max.
3. Any callbacks that uses higher time on site and memory than the thresholds, is considered a**
    **bad bot/user.
4. List out countries, devices and provider that have been used by said bots.**

### _Countries and their frequency of bad bots:_

'Brazil': 18, 'India': 7, 'Hong Kong': 1, 'Malaysia': 1, 'Panama': 1, 'Japan': 1, 'Singapore': 1, 'United States': 1'Taiwan': 6, 'Colombia': 4, 'Canada': 3, 'Chile': 3, 'Mexico': 3, 'Others': 2, 'Australia': 2, 'Philippines': 1, 'South Africa': 1,

### (^) _Service providers and their frequency of bad bots:_
'Taiwan Mobile': 1, 'Mobile Business': 1, 'Philippine Long': 1, 'Telstra Corporation': 1, 'COMCEL S.A.': 1, 'Others': 8, 'TELEFÃƒâ€œNICA, CHILE': 1,
'DiGi Telecommunications': 1, 'Reliance Jio': 1, 'TELEFÃƒâ€\x9dNICA BRASIL': 1, 'CLARO S.A.': 1, 'Tim Celular': 1, 'CentennialCayman': 1, 'Data
Communication': 1, 'Colombia MÃƒÂ³vil': 1, 'TPG Telecom': 1, 'Vodafone India': 1, 'CLARO CHILE': 1, 'TOTALPLAY': 1, 'Uninet S.A.': 1, 'Far
EastTone': 1, 'Cable Onda': 1, 'Telmex Colombia': 1, 'Brasil Telecom': 1, 'Bharti Airtel': 1, 'Mega Cable,':1, 'Bell Canada': 1, 'Telemar Norte': 1



### _Devices and their frequency of bad bots:_
'SM': 1, 'Others': 2, 'INE': 1, 'ANE': 1, 'ONEPLUS': 1, 'MI': 1, 'vivo': 1, 'moto': 1, 'ASUS': 1, 'G8142': 1, 'JSN': 1, 'Redmi': 1, 'Pixel': 1, 'MAR': 1,'Moto': 1, 'LG': 1, 'HTC': 1, 'motorola': 1, 'LM': 1, 'Mi': 1


