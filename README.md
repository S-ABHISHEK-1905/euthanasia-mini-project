<h1><p align="center">EUTHANASIA / MERCY KILLING - DATA SCIENCE MINI PROJECT</p></h1>


<p align="center"><img src="https://user-images.githubusercontent.com/66360846/204680175-5cc8fb49-732b-4942-9af0-1d94f7b44bfa.png" alt="Mercy KIlling logo"></p>

 

## DESCRIPTION ABOUT THE PROJECT

![image](https://user-images.githubusercontent.com/66360846/204679027-dfb3a346-7767-4797-9591-614ffe1a32a0.png)

![image](https://user-images.githubusercontent.com/66360846/204679185-5afc61c6-f783-4aed-91f2-3b946ecd9b3b.png)

![image](https://user-images.githubusercontent.com/66360846/204679200-33232a8d-be33-428b-b1ab-c244be2696b4.png)



## PROGRAM WITH OUTPUT

![image](https://user-images.githubusercontent.com/66360846/201723211-73ba837d-10d9-4c8f-8841-022f99db3819.png)

![image](https://user-images.githubusercontent.com/66360846/201723356-faaebab5-c8fe-43bf-9f91-96712b7e4110.png)

![image](https://user-images.githubusercontent.com/66360846/201723498-d8a7f58f-76b3-40f7-b9b6-cb6a2dc09cd4.png)

### BOX PLOT

```
import seaborn as sns
sns.boxplot(x="On a scale of 1-10 rate the following statement MERCY DEATH IS ALSO A SORTOF KILLING AND NEVER BE LEGALISED",y="Age?",data=d)
```
![image](https://user-images.githubusercontent.com/66360846/201723719-ca2e7784-a39e-4da7-8296-d3027a74c305.png)


```
d.boxplot()
```
![image](https://user-images.githubusercontent.com/66360846/201723997-7e3f317a-a640-4fa4-b8ef-708c31f165ca.png)


### UNIVARIATE ANALYSIS
#### PIE CHART 

```
import matplotlib.pyplot as plt
d_count = d.groupby(by=["Do you think euthanasia should be completely legalised in India ?"]).count()
d_sum = d.groupby(by=["Do you think euthanasia should be completely legalised in India ?"]).sum()

labels=[]

for i in d_count.index:
    labels.append(i)

plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.title("Do you think euthanasia should be completely legalised in India ?")
plt.pie(d_count["On a scale of 1-10 rate the following statement MERCY DEATH IS ALSO A SORTOF KILLING AND NEVER BE LEGALISED"], colors = colors, labels=labels, autopct = "%0.0f%%",shadow = True) 
plt.show()
```
![image](https://user-images.githubusercontent.com/66360846/201724255-4774cd29-87c6-4b29-8f8a-a59bd822489a.png)


```
d_count = d.groupby(by=["If yes , do you think the guidlines should be relaxed or more stringent ?"]).count()
d_sum = d.groupby(by=["If yes , do you think the guidlines should be relaxed or more stringent ?"]).sum()

labels=[]

for i in d_count.index:
    labels.append(i)

plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.title("If yes , do you think the guidlines should be relaxed or more stringent ?")
plt.pie(d_count["On a scale of 1-10 rate the following statement MERCY DEATH IS ALSO A SORTOF KILLING AND NEVER BE LEGALISED"], colors = colors, labels=labels, autopct = "%0.0f%%",shadow = True) 
plt.show()
```
![image](https://user-images.githubusercontent.com/66360846/201724724-501d601a-79fa-45c0-9aa2-fbefd1a93726.png)


```
d_count = d.groupby(by=["On a scale of 1-10 rate the following statement MERCY DEATH IS ALSO A SORTOF KILLING AND NEVER BE LEGALISED"]).count()
d_sum = d.groupby(by=["On a scale of 1-10 rate the following statement MERCY DEATH IS ALSO A SORTOF KILLING AND NEVER BE LEGALISED"]).sum()

labels=[]

for i in d_count.index:
    labels.append(i)

plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.title("On a scale of 1-10 rate the following statement MERCY DEATH IS ALSO A SORTOF KILLING AND NEVER BE LEGALISED")
plt.pie(d_count["Are aware of the guildlines for mercy killing in india ?"], colors = colors, labels=labels, autopct = "%0.0f%%",shadow = True) 
plt.show()
```
![image](https://user-images.githubusercontent.com/66360846/201724805-7efa719a-e1c3-43d8-8a53-c1ed0a2f192c.png)

```
d_count = d.groupby(by=["All those who are suffering from terminal diseases should be allowed to end their lives if they desire to?"]).count()
d_sum = d.groupby(by=["All those who are suffering from terminal diseases should be allowed to end their lives if they desire to?"]).sum()

labels=[]

for i in d_count.index:
    labels.append(i)

plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.title("All those who are suffering from terminal diseases should be allowed to end their lives if they desire to ")
plt.pie(d_count["Are aware of the guildlines for mercy killing in india ?"], colors = colors, labels=labels, autopct = "%0.0f%%",shadow = True) 
plt.show()
```
![image](https://user-images.githubusercontent.com/66360846/201724862-49168ca6-e271-4df7-b13a-17f8555da0ae.png)


### MULTIVARIATE ANALYSIS
#### BAR PLOT

```
sns.barplot(x=d["Age?"],y=d["On a scale of 1-10 rate the following statement MERCY DEATH IS ALSO A SORTOF KILLING AND NEVER BE LEGALISED"],data=d)
```
![image](https://user-images.githubusercontent.com/66360846/201724976-1c6054ff-1efc-4421-88d0-4035cc5c0a0f.png)


```
sns.barplot(x=d["On a scale of 1-10 rate the following statement MERCY DEATH IS ALSO A SORTOF KILLING AND NEVER BE LEGALISED"],y=d["Email Address"],data=d)
```
![image](https://user-images.githubusercontent.com/66360846/201725048-ad23b99f-8008-4a8f-b162-4955ec66c10e.png)


```
a=d.loc[:,["Email Address","On a scale of 1-10 rate the following statement MERCY DEATH IS ALSO A SORTOF KILLING AND NEVER BE LEGALISED"]]
a=a.groupby(by=["Email Address"]).sum().sort_values(by="On a scale of 1-10 rate the following statement MERCY DEATH IS ALSO A SORTOF KILLING AND NEVER BE LEGALISED")
plt.figure(figsize=(17,7))
sns.barplot(x=a.index,y="On a scale of 1-10 rate the following statement MERCY DEATH IS ALSO A SORTOF KILLING AND NEVER BE LEGALISED",data=a)
plt.xticks(rotation = 90)
plt.xlabel=("Email Address")
plt.ylabel=("On a scale of 1-10 rate the following statement MERCY DEATH IS ALSO A SORTOF KILLING AND NEVER BE LEGALISED")
plt.show()
```
![image](https://user-images.githubusercontent.com/66360846/201725132-122645ed-2f69-45b0-8fd5-57eb1c76b80a.png)


#### HEAT MAP
```
import numpy as np
data = np.random.randint(low = 1, high = 100, size = (10, 10))
print("The data to be plotted:\n")
print(data)
hm = sns.heatmap(data = data)
plt.show()
```
The data to be plotted:

[[18 24 83 39 31 47 96 72 69  4]
 [21 63 42 84 67 28 53 58 96 16]
 [69 59 75 47  1 62 72 16 63 71]
 [78  8 60  1 11 57 89 96 52 67]
 [29 31 52 79 80 12 24 38 14 52]
 [87 53 57 79 52 93 68 26 41 61]
 [98 24 36 66 68 79 62 19 93 20]
 [82 73 12 53 65 34 17 87 34 63]
 [28 28 51 49 29 57 62 31  9 77]
 [62 28 73  8 96 97 35  6 52 68]]
 
 ![image](https://user-images.githubusercontent.com/66360846/203369157-b4835cee-eaf8-4fb3-b12a-17b06d6f2b78.png)



### DATA VISUALIZATION
#### POINT PLOT

```
sns.pointplot(x=d['Age?'],y=d['On a scale of 1-10 rate the following statement MERCY DEATH IS ALSO A SORTOF KILLING AND NEVER BE LEGALISED'])
```
![image](https://user-images.githubusercontent.com/66360846/201725535-c87e1d10-1af1-4d03-9f38-055299270e85.png)


#### COUNT PLOT

```
sns.countplot(x='On a scale of 1-10 rate the following statement MERCY DEATH IS ALSO A SORTOF KILLING AND NEVER BE LEGALISED',data=d)
```
![image](https://user-images.githubusercontent.com/66360846/201725642-fd6be289-a3dc-4ac6-93aa-56a402d758f6.png)


#### HISTOGRAM

```
sns.histplot(x='On a scale of 1-10 rate the following statement MERCY DEATH IS ALSO A SORTOF KILLING AND NEVER BE LEGALISED',data=d)
```
![image](https://user-images.githubusercontent.com/66360846/201725773-8893d3fa-22ff-4c40-b413-ee56a30a678b.png)


#### KDE PLOT

```
sns.kdeplot(x='On a scale of 1-10 rate the following statement MERCY DEATH IS ALSO A SORTOF KILLING AND NEVER BE LEGALISED',data=d)
```

![image](https://user-images.githubusercontent.com/66360846/201725860-861f7a05-ed81-4529-8801-4229fd46890b.png)


<center>
<h1> THE END </h1>
</center>
