---
layout: home
permalink: index.html

# Please update this with your repository name and title
repository-name: e17-co328-Document-Tag-Generator
title:
---

[comment]: # "This is the standard layout for the project, but you can clean this and use your own template"

# Document Tag Generator

---

![Sample Image](./images/sample.png)


## Team
-  e17100, Gunathilaka R.M.S.M, [e17100@eng.pdn.ac.lk](mailto:e17100@eng.pdn.ac.lk)
-  e17246, Perera K.S.D, [e171246@eng.pdn.ac.lk](mailto:e17246@eng.pdn.ac.lk)
-  e17284, Rathnayake R.L.D.A.S, [e17284@eng.pdn.ac.lk](mailto:e17284@eng.pdn.ac.lk)

# Table of Contents
1. [Introduction](#introduction)
2. [Local Installation](#other-sub-topics)
3. [Links](#links)

---

# Introduction
### ✨ Problem
The project website of the Department of Computer Engineering currently has nearly 150 projects. These projects are categorized by only batches and subjectwise. Also, some of the projects have some tags but some of them are not relevant to those projects. Also, some projects do not have any tags. Currently, users can search projects by keywords, but those keywords are derived only from project descriptions.

![Screenshot 2022-03-14 222117](https://user-images.githubusercontent.com/73388013/158221303-0c3f3225-ced8-44e4-a7aa-9d9b075e4373.png)


* [Project Website](https://projects.ce.pdn.ac.lk/)


### ✨ Our goal
Our goal is to generate relevant tags for each project according to the description of the projects and other valid data available on the project pages. 


### ✨ Solution
Our plan is to build an ML model to generate relevant tags. The data needed to implement the ML model is retrieved from the project pages and the project repositories. To get all details (link to the repositories and project pages + other details) of the project pages and repositories API of the website is used. To get the data from the project pages a scraping tool will be used.
* [API repository](https://github.com/cepdnaclk/projects.ce.pdn.ac.lk)
* [API site](https://api.ce.pdn.ac.lk/)

<br></br>
___
***Project Owner : Mr. Nuwan Jaliyagoda*<br>
*Scrum Master: Mr. Thushara Bandara***
___
<br/>

## ✨Our Team
#### E/17/100 - Gunathilaka R.M.S.M
#### E/17/246 - Perera K.S.D
#### E/17/284 - Rathnayaka R.L.D.A.S
---

<br/>
<br/>

# Local Installation 

The site is built by Jekyll Builder and hosted on GitHub pages.
* Fork the repository and clone that into your local machine.
* Follow the  build instruction  to install the necessary dependencies to run the Jekyll builder in your local machine
##**Build Instruction**
---
```
gem install just-the-docs
gem install jekyll-sitemap
bundle exec just-the-docs rake search:init jekyll-sitemap
```
---
*Note: - If you face any dependency/version issue follow the instruction in [this](https://github.com/rbenv/rbenv) link to downgrade/upgrade the versions*

**current version is 2.7.1**
```
rbenv install 2.7.1
rbnev global 2.7.1
```
For the API install this additional python packages
```
pip install requests
cd ./python_scripts/
python3 stat_script.py
```

<br/>
<br/>

# Architecture
___
![architecture](https://user-images.githubusercontent.com/73388013/158223147-1123d1e7-a87d-402c-9153-efbff82887ce.png)

___

In department projects website, frontend, and backend are already implemented. According to the current implementation, users can search projects using tags. But the tagging was done using a simple algorithm such that it checks whether the project description contains the searching tag. Our goal is to implement a machine learning model, which can do tagging in a much better way.


In order to train the machine learning model we need a data set that contains the details of the projects. We hope to use project descriptions, project repositories, and project pages to generate the data set. By using this dataset, we have to train a good ML model, which can tag projects in the department website in a better way. 

After implementing the ML model, we have to integrate it with the backend of the department website. Then we need to run the ML model to generate tags and those tags should be stored in a [json file] inside the [backend repository].

Backend of the department project website can be accessed by a [API]. It contains a [end point] to access that json file which contains all the generated tags and their corresponding tags. When a user search a project using tags, by using tags file, relevant projects will be shown to the user.

When new project is added to the department project website, we need to run the ML model again and update the tags file. GitHub actions can be used for that. 

Since project pages and project repositories are update regularly, we hope to run the ML model weekly. 






[//]: # 
[API]: <https://api.ce.pdn.ac.lk/docs/projects/>
[end point]: <https://api.ce.pdn.ac.lk/projects/v1/filter/tags/>
[json file]: <https://github.com/SachinthaMadhushanka/api.ce.pdn.ac.lk/blob/main/projects/v1/filter/tags/index.json>
[backend repository]: <https://github.com/SachinthaMadhushanka/api.ce.pdn.ac.lk>


.....

## Links

- [Project Repository](https://github.com/cepdnaclk/e17-co328-Document-Tag-Generator/)
- [Project Page](https://cepdnaclk.github.io/e17-co328-Document-Tag-Generator/)
- [Department of Computer Engineering](http://www.ce.pdn.ac.lk/)
- [University of Peradeniya](https://eng.pdn.ac.lk/)


[//]: # (Please refer this to learn more about Markdown syntax)
[//]: # (https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
