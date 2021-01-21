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

for this problem, my approach would be make the financial distress score which predict financial distress of individual by the end of current month or specific cycle (i.e. quarterly )into scale of 1-100, which 1 means very dangerous financial distress and 100 means very healthy financial. for example if load the prediction on 15 January based on my January financial transaction then the model will predict what kind of score that it will be on the end of January. Which give user helpful insight about how should they spend etc.
thus for this problem would like to use a linear regression to predict the  financial distress  score. 

before building the model, the dataset could be built based on the past available transaction history for example we could make dataset based on transactions or any data from first of the month and to date 15 of the months, and the label would be based from financial distress assessment from expert or financial distress ratio formula. 

For training linear regression model we can choose scikit-learn to build the preliminary model and then gradually moving into tensorflow, pytorch or any deep learning regression model in favor for updating the model regularly since in theory we could easily re-train deep learning model easily based on saved state or weights with new data that we generated each day.

By looking at the scoring, people could asses what kind financial situation that they have currently. Further we could help them more detailed information for example they need limit their spending on food etc. Thus they could avoid fall into huge debt or bad financial distress situation. we can monetize some part of this useful detailed information, so people still freely have this information but if they need more they need to paid or use any monetize method given. another things we could do is cooperate our financial distress score as API to bank or any financial applications as means to enrich their application features which help satisfy their customer.

Most Challenging part is that most people especially in Indonesia have huge amount of unrecorded financial transactions for example buying street food which most of the time it will use a cash based transaction. Most likely this kind of transaction goes unrecorded. Some method we could provide is to build information extraction (using OCR to extract text and NLP based classification to classify what kind of information in the photo) from receipt photo of their transactions to digitalize their transaction easily.