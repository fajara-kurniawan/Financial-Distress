# Financial-Distress

Financial Distress for Individuals

Given the definition of Financial Distress, while is certainly a well known parameter for companies, the challenge for you is to propose how you would go about building and model for Prediction of Financial Distress for Individuals, giving them a score and productising it via an API.

You don’t have to implement anything but requirements are as follows:

1. Create a public repo in Github where you add a README.md. Paste this assessment in the .md file and describe your solution, answer questions, add notebooks if needed, snippets, samples, references, links, etc.
2. Assuming you have access to banking data (transactions) and also from any other source: telco, personal data, etc. (including other digital platforms), identify features/parameters (not extensively but most important ones to consider) to be part of your proposed solution.
3. Which algorithm(s) would you propose.
4. How would you build and train your model.
5. How would you productise the predictive financial distress model in order to consume it and update it (real time) with more data.
6. Which part is the most challenging? (please answer in the README.md)
7. How do you think this is gonna impact people's lives? (please answer in the README.md)


While describing your solution you have to specify tech stack/tools used (and justify).

Please don’t spend too much time on this, it’s mostly informative and for you to research and propose an initial approach.

-----------------------------------------

ANSWER 

------------------------------------

for this problem, my approach would be make the financial distress score which predict financial distress of individual by the end of current month or specific cycle (i.e. quarterly ) into scale of 1-100, which 1 means very dangerous financial distress and 100 means very healthy financial. for example if load the prediction on 15 January based on my January financial transaction then the model will predict what kind of score that it will be on the end of January. Which give user helpful insight about how should they spend etc. 

In order to build financial distress scoring from 1 to 100, we could take few approach:

- take the problem as regression problem with suppressing output value lower than 1 as 1 and output value higher than 100 as 100. for this we could use a  linear regression libraries like scikit-learn or deep learning based using tensorflow or pytorch. 
- take the problem as classification problem with 2 class ( i.e. bad financial and good financial) with probability for good financial class used as score. for example the output prediction is 78% being good financial class then we show the score as 78.  for this we could use a any kind of classical classification algorithm (SVM, Random Forest) or deep-learning based classification. 

Based on those 2 options and more thought about it, I changed my mind and prefer seeing this problem as  classification problems with probability as a score. i am thinking that to deal with some extreme data would be better using classification with probability as financial distress score. since there is possibility that regression will give such huge number and when we suppress them to either 0 or 100 it will lost its unique aspect or meaning

Before we build the classification model, we need to build some of the features for example with some following features to be used :

- Recurring monthly individual income 
- Recurring monthly individual expense  
- Average monthly income
- Average monthly expense
- Average Daily expense
- Average Monthly Expense on each category (food, shopping,transportation etc)
- Average Daily Expense on each category (food, shopping,transportation etc)
- work status (business or worker)
- Living area category (High class, medium class, etc)
- Work area category (High class, medium class, etc)
- Number of dependent people to take care of (family for example)
- Individual Asset converted into financial power (money)
- current date in months

Basically the features used is mostly about stability of income and expense on regular time interval. Since we can easily seen financial prowess of user based on their income or expense pattern and their environment.

After we build the features then we need to build the dataset. we could build dataset based on the past available transaction history. For example we could make data based on transactions or any data from first of the month  to 15th of the months and take the features we need and label it based from the help of expert or financial distress ratio formula and mapping it into good financial or bad financial class. 

Next step is we will build our classification problem, For this i have 2 options :

- Use traditional classification algorithm to build the preliminary model and then gradually moving into Tensorflow, Pytorch or any deep learning regression model. For traditional classification algorithm, I highly preferred we started from Trees-based algorithm like Random Forest or XGBoost as base models from my experiences since both of them have really good accuracy with fast training times. 
- Deep dive into deep learning classification model.

The need to use deep learning regression model is in favor for updating the model regularly since in theory we could easily re-train existing deep learning model from saved state or weights with new data that we generated.

With the help of financial distress score, user could asses what kind financial situation that they have currently. Further we could help them more detailed information for example they need limit their spending on food etc. Thus they could avoid fall into huge debt or bad financial distress situation. 

we can monetize some part of this useful detailed information, so people still freely have this information but if they need more they need to paid or use any monetize method given. another things we could do is cooperate our financial distress score as API to bank or any financial applications as means to enrich their application features which help satisfy their customer.

Most Challenging part is that most people especially in Indonesia have huge amount of unrecorded financial transactions for example buying street food which most of the time it will use a cash based transaction. Most likely this kind of transaction goes unrecorded. Some method we could provide is to build information extraction (using OCR to extract text and text classification to classify what kind of information each text has) from receipt photo of their transactions to digitalize their transaction easily.

