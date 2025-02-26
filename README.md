
# Python Currencies Telegram Bot

This repository contains a Telegram Bot that was developed to understand the Telegram Bot API, and Python web services.


## Prerequisites

- Get yourself a Bot account and a token at [Telegram Bots](https://core.telegram.org/bots).
- If you want to run it in Docker ->Docker installed on your system.
- If you want to run it without Docker -> Python 3.11 or higher.
- Optional: A server or cloud environment for hosting (e.g., Heroku, AWS, etc.).


## Methods to Run the Bot

You have three ways to run this bot: 

1. **Run the bot with a pre-built Docker image**
2. **Run the bot using Docker Compose**
3. **Build the Docker image and run the bot**
4. **Run locally without Docker**

<details open>
  <summary>1. With a pre-built Docker image</summary> 

You need to provide the following environment variable for the bot to work:

TOKEN: Your Telegram bot token from BotFather.

```bash
docker run -d --restart unless-stopped --name currencies -p 8443:8443 -e TOKEN="your-telegram-bot-token" gdagtekin/currency-bot
```

Check your log

```bash
docker logs -f currencies
```

</details>

---

<details>
  <summary>2. Docker Compose</summary> 

You need to provide the following environment variable for the bot to work:

TOKEN: Your Telegram bot token from BotFather.

```yaml
version: '3.9'
services:
  currencies:
    image: gdagtekin/currency-bot:latest
    restart: unless-stopped
    container_name: currencies
    ports:
      - "8443:8443"
    environment:
      - TOKEN=your-telegram-bot-token
```


Start the bot with Docker Compose

```bash
docker-compose up -d
```

Check your log

```bash
docker logs -f currencies
```

</details>

---

<details>
  <summary>3. Build the Docker image and run the bot</summary> 

You need to provide the following environment variable for the bot to work:

TOKEN: Your Telegram bot token from BotFather.

Clone the project

```bash
  git clone https://github.com/gdagtekin/Python-Currencies-Telegram-Bot
```

Go to the project directory

```bash
  cd Python-Currencies-Telegram-Bot
```
## Running with Docker

Build the Docker Image

```bash
docker build -t currency-bot .
```

Run the following command to start the bot in the container

You need to provide the following environment variable for the bot to work:

TOKEN: Your Telegram bot token from BotFather.

### Run the Docker Container

```bash
docker run -d --restart unless-stopped --name currencies -p 8443:8443 -e TOKEN="your-telegram-bot-token" currency-bot
```

Check your log

```bash
docker logs -f currencies
```

</details>

---

<details>
  <summary>4. Run locally without Docker</summary> 

You need to provide the following environment variable for the bot to work:

TOKEN: Your Telegram bot token from BotFather.

Clone the project

```bash
  git clone https://github.com/gdagtekin/Python-Currencies-Telegram-Bot
```

Go to the project directory

```bash
  cd Python-Currencies-Telegram-Bot
```

Install pipenv

```bash
  pip install pipenv
```

Install dependencies

```bash
  pipenv install
```

Replace YOUR-TELEGRAM-BOT-TOKEN in the Const.py file with your Telegram Bot Token.

Start the bot

```bash
  python CurrenciesBot.py
```

</details>

---

## Test the Bot
Once the bot is up and running, you can start interacting with it. 

Send `/start` to see a welcome message and `/ping` to check if the bot is responding.

## Commands

- `/start` - Get a welcome message with bot instructions.
- `/ping` - Check if the bot is running and responding.
- `/dolar` - Get the current exchange rate of the US Dollar (USD) to Turkish Lira (TRY).
- `/euro` - Get the current exchange rate of the Euro (EUR) to Turkish Lira (TRY).
- `/gramaltin` - Get the current price of Gram Altın in Turkish Lira.
- `/ceyrekaltin` - Get the current price of Çeyrek Altın in Turkish Lira.
- `/ons` - Get the current price of Gold Ounce (ONS) in Turkish Lira.

---

## License

[MIT](https://choosealicense.com/licenses/mit/)