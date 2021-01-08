About
------------------
A basic chatbot using Rasa for accessing info about languages from the [World Atlas of Languages](https://wals.info/) data. This chatbot is built as part of the NLP course for [Plaksha University](https://plaksha.org/) taught by [Monojit Choudhary](https://www.microsoft.com/en-us/research/people/monojitc/).

**[Please take help of course TA for any doubts]**

**[This is the complete version that can be used to just start chatting with the chatbot (has all the prerequisite code).]**

Installation
------------------

 - [Windows Installation Instructions](Install_windows.md)
 - [Linux Installation Instructions](Install_linux.md)
 - [MacOS Installation Instructions](Install_macos.md)

How to run Locally
------------------ 

**Note: You need to first go to the complete_version folder in your terminal and then run the following commands.**

1. You can train the models by running:  
```rasa train```  
This will train the Rasa NLU and Core models and store them inside inside the `models/` folder of your project directory.

3. In a new terminal (or anaconda prompt if on windows) start the server for the custom action by running:  
```rasa run actions```  
This will start the server for emulating the custom action.

4. Talk to the assistant by running:  
```rasa shell```  
This will load the assistant in your terminal for you to chat.

Deploying to Slack
------------------

1. Go to your Slack app's settings page and use the **Bot User OAuth Access Token** and **Signing Secret**:

And add this in the **credentials.yml** file:

```python
slack:
  slack_token: "Bot User OAuth Access Token"
  slack_signing_secret: "Signing Secret"
  slack_channel: 
```

2. Start the action server by typing the following command in terminal:

```
rasa run actions
```

3. Start the rasa server in another terminal window:

```
rasa run -m models --enable-api --cors "*" --debug
```

This will start the server at port 5005.

6. Now you have to expose this port to the world by using ngrok, open another terminal and type:

```
ngrok http 5005
```

7. Take the above url and paste it into the **Events Subscription** page of your slack app in the following format:

```
your_url_here/webhooks/slack/webhook
```

And you should now be able to talk to your chatbot in Slack! 

License
------------------
GPL-V3