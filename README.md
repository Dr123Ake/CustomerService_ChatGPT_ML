# **ML - Create a Customer Support Website with ChatGPT models**
[Google Slides](https://docs.google.com/presentation/d/110wkdPLv1HxS2wEj5NBrm1Br9f2UYO70l4Yxp-dtXrE/edit?usp=sharing)

## **Introduction**

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

<br>

## **Design**

<img width="496" alt="Screenshot 2023-03-26 005936" src="https://user-images.githubusercontent.com/54694766/227764799-f2d1bac3-819e-4ca6-ab60-974a1a9c1f6b.png">

1. **Install Packages**

   Set up environment with installing all the packages needed in the requirements.txt file. 

2. **Crawl Data**

   Crawl data from the website and save the data as a .csv file for use later. 

3. **Embedded Text**

   Use the text-embedding-ada-002
   Model to embedded the relevant data from the .csv file. 

4. **Display**

   Run the project with displaying the customer UI and collect questions.

<br>

## **Implementation and Test**

*This project is run on Ubuntu 22.04*

<img width="463" alt="Screenshot 2023-03-26 005018" src="https://user-images.githubusercontent.com/54694766/227764855-96251b57-d0ad-4968-b3cc-092afa7771d4.png">

<br>

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
<br>

2. **Crawl Data**

   ```
   $ python3 crawldata.py
   ```
   
   <img width="767" alt="Screenshot 2023-03-25 234136" src="https://user-images.githubusercontent.com/54694766/227764999-fb54131a-bad6-4ed5-8e96-a33a091ebe07.png">

<br>

3. **Embedded Text**
   ```
   $ python3 embedText.py
   ```
   <img width="643" alt="Screenshot 2023-03-25 214112" src="https://user-images.githubusercontent.com/54694766/227764970-bd90547a-6efc-4270-a86e-20a63a08562f.png">

   *No payment method linked, not working through since exceed limit of 60 requests per mins.Worked through after adding payment method.*

   <img width="889" alt="Screenshot 2023-03-25 220728" src="https://user-images.githubusercontent.com/54694766/227765062-3f7c47a9-890c-49d4-9a08-5ac1d5bd7ef7.png">

   Total cost for embedding the data.

   <img width="489" alt="Screenshot 2023-03-25 220826" src="https://user-images.githubusercontent.com/54694766/227764976-84454963-3e2b-4455-b39f-2d96e55b0688.png">


<br>

### **Tips on Saving Money for Developing**

OpenAI charges based on tokens, so to minimize the cost of deveopment for this project, I used a small size of data while developing to make the use of the grant given by the platform.

1. Run ```$ python3 crawaldata.py``` to make sure data crawling works

2. Create your own testing data and save it as ```processed/data.csv``` using the same structure as of ```processed/scraped.csv```. 

![Screenshot 2023-03-16 014014](https://user-images.githubusercontent.com/54694766/228060450-1c657372-08d7-41cf-b304-af291a6101e4.png)

<img width="188" alt="image" src="https://user-images.githubusercontent.com/54694766/228059942-d5662acf-14f2-4a91-8772-0bc83d7667ac.png">

3. Modify the code in ```embedText.py``` to read csv file ```processed/data.csv``` instead of ```processed/scraped.csv```.

<img width="501" alt="image" src="https://user-images.githubusercontent.com/54694766/228060086-213d5f85-beed-4afc-aabf-605ad3b2d60a.png">

4. Run ```$ python3 embedText.py``` to embed the data.

5. Run ```$ flask run``` to test the project by asking questions about the testing data in browser. 

<img width="481" alt="Screenshot 2023-03-19 211449" src="https://user-images.githubusercontent.com/54694766/228060541-47a04fdb-185f-474f-9de5-4954b2c27f6c.png">

6. Once the project is working as desired, link your payment method on OpenAI and embed ```processed/scraped.csv``` then test project with ```$ flask run```.

<br>

4. **Display**

   ```
   $ flask run
   ```
   
   <img width="611" alt="Screenshot 2023-03-26 000404" src="https://user-images.githubusercontent.com/54694766/227764905-94f1632d-cf85-48fb-a34d-740385d0857b.png">

   You should now be able to access the app at [http://localhost:5000](http://localhost:5000)

   ***Sample Questions and Answers:***
   
   <img width="352" alt="Screenshot 2023-03-25 222209" src="https://user-images.githubusercontent.com/54694766/227764916-a4cbfc3a-2e1e-4344-a738-dd6619be1d96.png">

   <img width="366" alt="Screenshot 2023-03-25 222020" src="https://user-images.githubusercontent.com/54694766/227764928-509f5980-0cd8-462d-a264-e5b4b42e5736.png">

   <img width="403" alt="Screenshot 2023-03-25 221942" src="https://user-images.githubusercontent.com/54694766/227764931-6dbba85a-6851-4adf-935d-f25a1280c900.png">

   <img width="363" alt="Screenshot 2023-03-25 221754" src="https://user-images.githubusercontent.com/54694766/227764935-12b2d24e-be85-4813-8ebe-d551db49661f.png">

<br>

## **Conclusion**

**Accuracy**

* As the questions I asked based on my own data and data crawled from the website, the answer is quite accurate.
* I think the accuracy is more determined by the data provided by the website.

**Cost**

* To avoid high charges, we can use less data while developing. 
Use the real data only when the whole project go through as desired. 
* In this project, the embedding text can be run only once to save money.

*Final cost*

<img width="529" alt="Screenshot 2023-03-26 003555" src="https://user-images.githubusercontent.com/54694766/227764890-c2dc08aa-38f7-44e0-8be4-801e77c71ae2.png">

<br>

## **Enhancement**

* Improve UI
* Implementate more APIs for customer services

<br>

## **References**
* https://platform.openai.com/docs/guides/embeddings/what-are-embeddings 
* https://help.openai.com/en/articles/6779149-how-do-text-davinci-002-and-text-davinci-003-differ  
