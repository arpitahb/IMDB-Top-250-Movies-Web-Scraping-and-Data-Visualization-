# IMDB Top 250 Movies Web Scraping and Data Visualization Project

## Table of Contents
+ [About](#about)
+ [Getting Started](#getting_started)
+ [Libraries](#libraries)
+ [Procedure](#procedure)
+ [Resources](#resources)

## About <a name = "about"></a>
A simple project that I did while learning Web scraping and Data Visualization. In this mission, I learned various concepts of web scraping and get comfortable with scraping various types of websites and their data.On the other hand I also understood the concept and use of data visualization tools and libraries
### Web Scraping
Web scraping is an automatic method to obtain large amounts of data from websites. Most of this data is unstructured data in an HTML format which is then converted into structured data in a spreadsheet or a database so that it can be used in various applications. There are many different ways to perform web scraping to obtain data from websites. In this project, I extracted data from the website https://www.imdb.com/chart/top/?ref_=nv_mv_250 . The data obtained were: Movie name, Year of release, Ranking and IMDB Rating

### Data Visualization
Data visualization is the representation of data through use of common graphics, such as charts, plots, infographics, and even animations. These visual displays of information communicate complex data relationships and data-driven insights in a way that is easy to understand.In this Project, I used the library matplotlib to perform simple data visualization operations on the obtained data

## Getting Started <a name = "getting_started"></a>
These steps are followed before undertaking the project:

### Prerequisites

What things you need to install the software and how to install them.

#### 1. Anaconda Navigator
It is a desktop application which  lets you easily manage integrated applications, packages, and environments without using the command line.
It can be installed from https://www.anaconda.com/products/distribution

#### 2. Anaconda prompt
Anaconda command prompt is just like command prompt, but it makes sure that you are able to use anaconda and conda commands from the prompt, without having to change directories or your path. 
We can check if the anaconda navigator is installed properly using command

```
conda install --help
```

#### 3. Create environment
Virtualenv is a tool to create isolated Python environments. With the help of virtualenv, we can create a folder that contains all necessary executables to use the packages that our Python project requires. Here we can add and modify python modules without affecting any global installation.

To create:
```
conda create --name envnew
```
To activate:

```
conda activate envnew
```


#### 4. pip
We use pip command to install all the modules and libraries.

```
conda install pip
```

#### 5. Jupyter Notebook
The Jupyter Notebook App is a server-client application that allows editing and running notebook documents via a web browser. The Jupyter Notebook App can be executed on a local desktop requiring no internet access (as described in this document) or can be installed on a remote server and accessed through the internet.
Our project is done using Jupyter notebook

To install:
```
conda install jupyter notebok
```
To activate:
```
jupyter notebook
```

### RoadMap

#### WEB SCRAPING
1. Go To IMDB Top 250 Movies Page and copy the URL
2. import libraries BeautifulSoup and requests in Jupyter Notebook
3. request to get the page and save the html format
4. In the webpage, click inspect the <!DOCTYPE html>
5. Get the Movie Name, Year of release, rank and rating 

#### DATA VISUALIZATION
1. import pandas and matplotlib libraries
2. get the data from the webpage into a DataFrame
3. Produce a csv file
4. Use matplotlib library to perform basic data visualization operatio

## Libraries <a name = "libraries"></a>
1. Requests:- It is an efficient HTTP library used for accessing web page.
2. BeautifulSoup library:-  It is a Python library for pulling data out of HTML and XML files.
3. Pandas:- It is a fast, powerful, flexible and easy to use open source data analysis and manipulation tool,
built on top of the Python programming language.
4. matplotlib: It is a comprehensive library for creating static, animated, and interactive visualizations in Python.


## Procedure <a name = "procedure"></a>

First, Get the url of the website and using the requests library, access the webpage

```
imbd_url='https://www.imdb.com/chart/top/?ref_=nv_mv_250'

```
```
response= requests.get(imbd_url)
```

Using BeautifulSoup library , get the html doctype of the webpage

```

m= soup.find('tbody', {'class':"lister-list"}).find_all('tr')

```
Extract the required data from the webpage. Code for extraction is in IMDB top 250.ipyn file
Store the data in a dictionary and then convert the dictionary to a dataframe

```

dict={"Movie Name":names, "Year of Release": years, "IMDB Rating": rating, "Rank":rank}

df= pd.DataFrame(dict)
```

Convert to a csv file
[ImdbMovies.csv](https://github.com/arpitahb/IMDB-Top-250-Movies-Web-Scraping-and-Data-Visualization-/files/9368036/ImdbMovies.csv)


### Data Visualization 

Using matplotlib.pyplot, we perform some simple data visualization operations:
 
 To Obtain The mean of the IMDB Rating. We first convert the column to datatype float and then use mean()
```
df['IMDB Rating']= df['IMDB Rating'].astype(float)
df['IMDB Rating'].mean()
```
Output: 8.253999999999976

Ploting a histogram of the imdb ratings:

```

df['IMDB Rating'].plot(kind='hist', bins=20)
```
![histogram_plot](https://user-images.githubusercontent.com/91077436/185306341-6e06960a-82a7-4ee2-9988-40188654ec57.png)

This histogram tells us that the most movies in this list has an IMDB Rating of 8

 The same data ploted in box form:
 
```
df['IMDB Rating'].plot(kind='box')

```

![box_plot](https://user-images.githubusercontent.com/91077436/185306615-dcd7ec5c-0a1f-4e91-95f4-87f1c4d5224f.png)

The green line is the median

Taking The top 10 Imdb Movies and ploting a graph:

```

df1= df.head(10)
```

```

x=df1['IMDB Rating']
y=df1['Year of Release']
plt.plot(x,y)
plt.xlabel('IMDB Ratings')
plt.ylabel('Year of Release')
plt.title("Top 10 IMDB Movies")

```
![top 10 movies](https://user-images.githubusercontent.com/91077436/185306970-270af7e4-a39d-4cd2-a8db-8a367c57d801.png)

#### Using  a visualization to detect whether there is a relationship between year of release and imdb rating:
Average IMDB Rating for movies released after 1994

```

df[df['Year of Release']>=1994]['IMDB Rating'].mean()

```


Average IMDB Rating for movies released before 1994


```
df[df['Year of Release']<1994]['IMDB Rating'].mean()
```

Plotting a graph:
```
df.boxplot(column='Year of Release', by='IMDB Rating')
```

![imdb-year](https://user-images.githubusercontent.com/91077436/185307601-6819ac8d-0b47-4fa9-8de7-25dbd3e5e392.png)

To find: The year of release of the maximum number of movies in Top 250 IMDB List

```
df['Year of Release'].value_counts()[df['Year of Release'].value_counts() == df['Year of Release'].value_counts().max()]
```
output:
1995.0    8
Name: Year of Release, dtype: int64

Plotting the movies released in 1995:
```
x=df2['Movie Name']
y=df2['Rank']
plt.plot(x,y)
plt.title("Movies Released in year 1995")
plt.xlabel("Movie Name")
plt.ylabel("Ranks")
plt.rcParams["figure.figsize"] = (100,10)
```

![1995](https://user-images.githubusercontent.com/91077436/185307944-f58eba93-3a02-4e70-b517-639220c23a27.png)


## Resources <a name = "resources"></a>
1. https://realpython.com/python-web-scraping-practical-introduction/
2. https://www.dataquest.io/blog/web-scraping-tutorial-python/
3. https://jovian.ai/aakashns/python-web-scraping-project-guide
4. https://github.com/AlexTheAnalyst/PortfolioProjects/blob/main/Amazon%20Web%20Scraper%20Project.ipynb
