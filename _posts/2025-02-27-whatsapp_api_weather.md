---
layout: post
title: Send Weather alerts from IPMA using API Twilio in WhatsApp.
date: 2025-02-27 21:22 +0000
last_modified_at: 2025-03-02 23:33 +0000
author : Luciano Nieto
tags: [whatsapp, python, api, app, twilio]
toc:  true
---

This project aims to provide an automated WhatsApp-based weather alert system, ensuring that users receive timely and accurate notifications about significant weather changes in the city of Lisbon. Source of forecasts: IPMA.

## Methodology:
- The methodology for this project follows a structured approach to ensure the accurate delivery of weather alerts via WhatsApp. The process consists of the following key steps:
    Data Collection: Weather data is fetched from external IPMA API.
    Alert Generation: Based on predefined conditions, alerts are triggered for specific location using Twilio API. (Paid / Trial)

## Requirements

To use this repo, you will need the following:

- Clone this repository to your local machine.
- Install the libraries listed on requirements.txt.
- Use a Twilio Trial account for test the messages.

## Code Structure

# IPMA API:

```python
"""Module to interact with IPMA API"""
from datetime import datetime
import logging
import requests
from services.settings import CITY_ID
from services.settings import IPMA_API_URL

def get_weather_forecast():
    """ Forecasts from IPMA """
    url = f"{IPMA_API_URL}{CITY_ID}.json"
    try:
        response = requests.get(url,timeout=30)
        response.raise_for_status()
        data = response.json()
        today_forecast = data['data'][0]
        data_weather = {
            "min_temp": today_forecast["tMin"],
            "max_temp": today_forecast["tMax"],
            "precipitation": today_forecast["precipitaProb"],
            "date": datetime.now().strftime("%Y-%m-%d"),
            "execution_time": datetime.now().strftime("%Y-%m-%d %H:%M:%S")

        }
        return data_weather
    except Exception as e:
        logging.error(f"Error: {e}")
        return None
```

# Twilio Service:

```python
from twilio.rest import Client
import logging
from services.settings import TWILIO_ACCOUNT_SID, TWILIO_AUTH_TOKEN, TWILIO_PHONE_NUMBER, USER_PHONE_NUMBER

logging.basicConfig(level=logging.INFO)

def send_whatsapp_message(message):
    """ Sent message by WhatsApp via Twilio """
    try:
        client = Client(TWILIO_ACCOUNT_SID, TWILIO_AUTH_TOKEN)
        msg = client.messages.create(
            from_=TWILIO_PHONE_NUMBER,
            body=message,
            to=USER_PHONE_NUMBER
        )
        logging.info(f"Message sent with success! ID: {msg.sid}")
    except Exception as e:
        logging.error(f"Error when tried to sent message via Twilio: {e}")
```

# MAIN:
```python

from services.weather_api import get_weather_forecast
from services.twilio_service import send_whatsapp_message
import logging

logging.basicConfig(level=logging.INFO)

def main():
    """ Get the weather forecast and send via WhatsApp """
    forecast = get_weather_forecast()
    if forecast:
        message = (
            f"Weather Lisbon Forecast for Today \n"
            f"Min: {forecast['min_temp']}°C | Max: {forecast['max_temp']}°C\n"
            f"Rain: {forecast['precipitation']}%\n"
            f"Execution Time (Source IPMA): {forecast['execution_time']}"
        )
        send_whatsapp_message(message)

if __name__ == "__main__":
    main()

```

# .env
Create the file .env in the repository to apply the credentials and IPMA url and load in the settings:

```python

"""Settings..."""
import os 
from dotenv import load_dotenv

# Load vars from .env
load_dotenv()

IPMA_API_URL = os.getenv("IPMA_API_URL")
IPMA_API_KEY = os.getenv("IPMA_API_KEY")
CITY_ID = "1110600" #Lisbon

#Twilio
TWILIO_ACCOUNT_SID=os.getenv("TWILIO_ACCOUNT_SID")
TWILIO_AUTH_TOKEN=os.getenv("TWILIO_AUTH_TOKEN")
TWILIO_PHONE_NUMBER=os.getenv("TWILIO_PHONE_NUMBER")
USER_PHONE_NUMBER=os.getenv("USER_PHONE_NUMBER")
```

## Result

![](/imgs/imgwpp.PNG)



## More

- GitHub Repo **[here](https://github.com/lucnietoX/alerts_wpp_weather)**.