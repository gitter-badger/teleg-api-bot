# teleg-api-bot

[![Join the chat at https://gitter.im/LibreLabUCM/teleg-api-bot](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/LibreLabUCM/teleg-api-bot?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

Telegram Api for new bot system

## Getting started

This project uses Python 3, so you should probably install that, if you haven't already.

You should probably take a look at our [Getting Started](https://github.com/LibreLabUCM/teleg-api-bot/wiki/Getting-started-with-the-Telegram-Bot-API) wiki page.

## Usage

Dependencies: Python 3.4, py-yaml

"main.py" is the main file to run. It is an example of a bot.

Example bot:

```python

#!/usr/bin/python
from telegbot import telegbot
from logger import logger
logger = logger()
import time,json

def receive_message(msg):
    if msg["date"] < time.time() - 2:
        return # old
    logger.msg(msg)
    if msg["text"] == "/help":
        bot.sendMessage(msg["chat"]["id"], "Text")


bot = telegbot('TOKEN')
bot.on_receive_message = receive_message
bot.run()

```

