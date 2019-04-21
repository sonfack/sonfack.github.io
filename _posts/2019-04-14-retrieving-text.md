---
layout: page
title: "Retrieving textual document"
---

Hi every one !
This post is about methods on how to retrieve textual document.  
#### What is information retrieval(IR)
**[An Introduction to Information Retrieval by Christopher D. Manning et al.]**  
Information retrieval (IR) is finding material (usually documents) of an unstructured nature (usually text) that satisfy
 an information need from within large collections (usually stored on computers).  

Once documents are indexed, the next step is generally the retrieval, that is to search for the document.  
In this post we explore 3 main methods:
- Boolean models 
- vector models 
- probabilistic models   


#### Textual retrieval methods   
  
##### Boolean models    
This models are based on boolean algebra. Each document is represented only by it set of indexed terms, no weight is 
taken in consideration.  
Every query is formulated using **AND**, **OR**, **NOT**  
Example :  
Suppose we have nationalities of a given school pare promotions P22, p23, p24, p25.  
Where 1 indicates the given nationality in the promotion and a 0 the absence of that nationality.  
A boolean representation will be the term-document *incidence matrix*. 
![term-document matrix](/retrievingtext/boolean.png)  
    
###### Avantages  
- Simple to implement
- Good performance
- Low computational complexity 
- Simple user query structure  
We can for example ask:  
**Information need** :What are the nationalities present from P22 too P24.  
*Information need* is the topic about which the user desires to know more. **[An Introduction to Information Retrieval by
 Christopher D. Manning et al.]**  
P22 : 0 1 1 1 0 1 0, P23 : 0 1 1 1 1 0 1, P24 : 0 1 1 1 1 0 1   
**Query** : 0 1 1 1 0 1 0 **AND** 0 1 1 1 1 0 1 **AND** 0 1 1 1 1 0 1 = 0 0 1 0 0 0 0  
*Query* is what the user conveys to the computer in an attempt to communicate the information need.
Answer : Guinea   
       
###### Draw backs 
- Boolean queries are difficult to conceive for non experts
- No partial matching 
- No indexed terms weight  
  