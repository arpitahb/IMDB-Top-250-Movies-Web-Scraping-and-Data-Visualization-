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

## Libraries <a name = "libraries"></a>
1. Requests:- It is an efficient HTTP library used for accessing web page.
2. BeautifulSoup library:-  It is a Python library for pulling data out of HTML and XML files.
3. Pandas:- It is a fast, powerful, flexible and easy to use open source data analysis and manipulation tool,
built on top of the Python programming language.
4. matplotlib: It is a comprehensive library for creating static, animated, and interactive visualizations in Python.
## Procedure <a name = "procedure"></a>

Add notes about how to use the system.
## Resources <a name = "resources"></a>
