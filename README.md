# A repository for Network Analysis Project 2018

## Problem Statement: 
* The Common Workflow Language (CWL)(https://github.com/common-workflow-language/), is a way to describe command line tools and connect them together to create workflows. Because CWL is a specification and not a specific piece of software, tools and workflows described using CWL are portable across a variety of platforms that support the CWL standard. 

## Data Source:
* The data was gathered for the Spring 2018 courses offered in the iSchool. The data (https://github.com/pratikshrivastava/NA_PROJECT_SP2018/blob/master/data/data.csv) file was created manually using the ischool course pages for the spring 2018 semester. The file contains Id, Name, Description and Instructor of the courses. 


## Approaches taken. 
1. **Cosine similarity:** We used the gensim library of python for creating the corpus, generating the simliarity scores between the different courses. Once, we had the cosine similiarity scores we used networkx for creating the graphs between the nodes whose scores where greater than the set threshold. 

This approach had a drawback, as the course description are designed to be different from any of the other courses. Due to this the similarity scores between the documents were very low. This can be observed from the below plot. 

	* histogram plot of similarity score between different courses.  
![alt text](https://github.com/pratikshrivastava/NA_PROJECT_SP2018/blob/master/images/hist_sim_measure.png)
	* Network Plot
![alt text](https://github.com/pratikshrivastava/NA_PROJECT_SP2018/blob/master/images/network_sim.png)

2. **Entity Based:** We used a Google NLP api, for retrieveing the specific noun, pro-noun etc from the course description which helped us to define the entities in them. Once we got the entities, we tried manually classify those entities into categories. 

