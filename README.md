# Crypto Boet
## A simple python bot for Telegram for talking about crypto in group chats

### What is Crypto Boet?
Crypto Boet is a chat bot for telegram that knows the price of crypto currencies

### How does it work?
Crypto Boet will listen for all messages in a given chat (either directly with him or in a chat room which you invite him to) starting with "/get".
tl;dr: Look at one of the existing commands, you must have a run(bot, chat_id, user, request_text, keyConfig, number_of_results) function.

### How do I make my own bot using this?
Go to https://console.developers.google.com and create a Google App Engine project. Then take that project id (it will be two random words and a number eg. gorilla-something-374635) and your Telegram Bot ID which the Bot Father gave you and do the following:

1. Copy app.yaml.template and rename the copy to to app.yaml.
2. Update {GOOGLE APP ENGINE PROJECT ID} in app.yaml.
3. Copy keys.ini.template and rename the copy to keys.ini.
4. Update {Your Telegram Bot ID here} in keys.ini 
OPTIONAL:
5. Update the rest of keys.ini with keys for each command you want to use.
6. Copy pre-push to the .git\hooks folder.
7. In .git\hooks\pre-push change were it says [[PythonInstallation]] to your Python install location in bash notation (e.g. /C/Python27) and your 
8. In .git\hooks\pre-push change were it says [[GoogleCloudSDKInstallation]] to your Google Cloud SDK install location in bash notation (e.g. /C/Program Files (x86))
9. In .git\hooks\pre-push change were it says [[GoogleAppEngineProjectName]] to your Google App Engine Project ID in bash notation (e.g. /C/Program Files (x86))
10. Now when you push it will automagicly build and deploy ImageBoet to the cloud! To the hindenpeter!

```bash
git clone (url for your thorin fork) ~/bot
cd ~/bot
(PATH TO PYTHON27 INSTALL)\scripts\pip.exe install -t lib python-telegram-bot google-api-python-client
(PATH TO GOOGLE APP ENGINE LAUNCHER INSTALL)appcfg.py -A {GOOGLE APP ENGINE PROJECT ID} update .
```

Finally go to https://{GOOGLE APP ENGINE PROJECT ID}.appspot.com/telegram_webhook?url=https://{GOOGLE APP ENGINE PROJECT ID}.appspot.com/webhook (replace both {GOOGLE APP ENGINE PROJECT ID}s with the Google App Engine Project ID) to tell Telegram where to send web hooks. This is all that is required to setup web hooks, you do not need to tell the Bot Father anything about web hooks.

### Why the name Crypto Boet?
Boet is Afrikaans for brother. This bot is for very fast paced informal (probably South African) group chats.
