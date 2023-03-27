# ML - Create a Customer Support Website with ChatGPT models
[Google Slides](https://docs.google.com/presentation/d/110wkdPLv1HxS2wEj5NBrm1Br9f2UYO70l4Yxp-dtXrE/edit?usp=sharing)

## Introduction

This project is to use the popular ChatGPT models to create a customer support website to answer questions from customers about their website.

### OpenAI API Models

#### *text-embedding-ada-002*

OpenAI’s text embeddings measure the relatedness of text strings. Embeddings are commonly used for:

* **Search** (where results are ranked by relevance to a query string)
* **Clustering** (where text strings are grouped by similarity)
* **Recommendations** (where items with related text strings are recommended)
* **Anomaly detection** (where outliers with little relatedness are identified)
* **Diversity measurement** (where similarity distributions are analyzed)
* **Classification** (where text strings are classified by their most similar label)

#### *text-davinci-003*

This model builds on top of previous InstructGPT models, and improves on a number of behaviors that we’ve heard are important to you as developers.

It includes the following improvements:
* It produces higher quality writing. This will help your applications deliver clearer, more engaging, and more compelling content.
* It can handle more complex instructions, meaning you can get even more creative with how you make use of its capabilities now.
* It’s better at longer form content generation, allowing you to take on tasks that would have previously been too difficult to achieve.


## Design


1. Install Packages

   Set up environment with installing all the packages needed in the requirements.txt file. 

2. Crawl Data

   Crawl data from the website and save the data as a .csv file for use later. 

3. Embedded Text

   Use the text-embedding-ada-002
Model to embedded the relevant data from the .csv file. 

4. Display

   Run the project with displaying the customer UI and collect questions.

## Implementation and Test

*This project is run on Ubuntu 22.04*

1. **Create Python Virtual Environment and install Packages**

   Install the needed packages if you don’t have it installed.
   ```
   $ sudo apt install python3.10-venv
   ```

   List all needed packages and versions in requirements.txt file.
   ```
   $ python3 -m venv venv
   $ . venv/bin/activate
   $ pip install -r requirements.txt
   ```

   You may need to update your setuptools to make the installation smooth. 
   ```
   $ pip show setuptools
   $ pip3 install –upgrade pip setuptools or 
   $ pip install --upgrade setuptools --user python
   ```

2. **Crawl Data**

   ```
   $ python3 crawldata.py
   ```

3. **Embedded Text**
   ```
   $ python3 embedText.py
   ```

   *No payment method linked, not working through since exceed limit of 60 requests per mins.Worked through after adding payment method.*

   Total cost for embedding the data.


4. **Display**

   ```
   $ flask run
   ```

   You should now be able to access the app at [http://localhost:5000](http://localhost:5000)

   *Sample Questions and Answers:*


## Conclusion

**Accuracy**

* As the questions I asked based on my own data and data crawled from the website, the answer is quite accurate.
* I think the accuracy is more determined by the data provided by the website.

**Cost**

* To avoid high charges, we can use less data while developing. 
Use the real data only when the whole project go through as desired. 
* In this project, the embedding text can be run only once to save money.

*Final cost*


## Enhancesment

* Improve UI
* Implementate more APIs for customer services# CustomerService_ChatGPT_ML
