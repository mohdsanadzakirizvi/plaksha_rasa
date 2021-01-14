Welcome to assignment A1! [Total Marks: 10 + 5 (bonus)]
-------------------------

- This assignment is going to reinforce some of the basic concepts of building a chatbot (using Rasa) that were discussed in the class.
- There are three compulsory parts to the assignment: 1. NLU task, 2. Dialogue task and 3. Evaluation task that are discussed further. The fourth task is optional for those who want to challenge themselves more.
- You may use the **complete version** of the chatbot for this assignment.
- Though it's not needed for the current assignment, feel free to refer the reading material to revise the concepts.

## Instructions for submitting the assignment

 - The deadline for this assignment is **20th Jan EOD**.
 - You will have to submit the whole working chatbot folder as a **zip** file in moodle, the link for which will be provided.

## 1. NLU task [Marks: 5]

- You are already familiar that Rasa tries to learn patterns from the NLU data to extract entities and intents from incoming user message.
- These training examples are added in the `data/nlu.yml` file.
- Your task is to add **atleast 20 different ways** in which the user might indicate the **lang_search** intent to the chatbot.
- You also will have to add **atleast 10 different languages** as **entities** in your training data.
- Note that your assignment will be evaluated on **uniqueness** of your training data and will be compared with your peer's submissions and might be penalised if high % of overlap is observed (same ways of invoking the intent or same languages as entities).
- A high score will be given for submissions that have a good variety of cases covered, as the main objective of this part is to make you "think how varied real world user messages can get" and design the data accordingly.

## 2. Dialogue task [Marks: 4]

- Chatbots in the real world learn improve continously from user feedback, and  we will learn how to emulate that behavior (albeit partially) in this part of the assignment.
- We have already learned about rules in the class for adding basic dialogue ability to the chatbot. These rules are added in the `data/rules.yml` file.
- In this part, you have to create a "feedback rule" - it should ask the user whether the chatbot was able to solve the user's query or not?
- Here's how this conversation flow will look like:

```
user: hey man
rasabot: Hi! How may I help you?

user: I want to know about hindi
rasabot: <gives details about hindi>

rasabot: Did that help you?
user: <user can respond yes or no>
```

- You will have to write a new rule for enabling this behaviour. You can start with the existing rules present in the file to get a better idea.
- Note that along with adding the new rule, you will also have to make minor adjustments in the `domain.yml` and `data/nlu.yml` files. Feel free to look at the existing code for ideas.

## 3. Evaluation [Marks: 1] 

- You must have noticed many corner cases for your chatbot even after all the training and additional data.
- In this assignment, you have to list 10 such queries or cases in which the chatbot fails or is unable to extract the correct intent/entity. 
- You also have to provide: 1. a one line description of what you think might be the reason for each fail and 2. what can be possible ways to mitigate the issue (eg. more training data, better NLU model etc.)?
- You can create a file "evaluation.txt" and submit it along with the rest of the chatbot.

## 4. More fun with WALS data [Optional; 5 Marks ~ Only for adventurous ones]

**[Below is a brownie task for the brave-hearted. It's "optional" for only those who want to explore a bit more and learn more.]** 

- Feel the above tasks are too easy for you? Do you yearn for something more interesting? 
- Then here's a task for you to get not only noticed by everyone but also learn much more about Rasa.
- You know that we have defined a custom action for looking up basic info of a language from WALS dataset in `actions.py` file. Guess what? we are just using a subset of the data available.
- Can you look into the raw WALS data (present in `data/cldf-datasets-wals-014143f`) and figure out a more interesting use case for the chatbot? 
- You might want to lookup WALS online to understand how that data can be used. 
- This challenge will not only require you to think analytically about the data but also think how to build a new end-to-end functionality for the chatbot: everything from nlu data to adding rules for the dialogue part and adding code in the actions.
- If you really want to take up this challenge, you are entitled to **one hint** from the TA!
- The best submissions will be highlighted in the next class. If you end up making something really useful, then we can maybe open source it too!
