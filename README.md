# algotrade

This purpose of this project is to use historical data and indicators to trade algorithmically using Binace API.

To run bot.py you will need to create a set of API keys on Binace.
Then you will store those in a config.py
api_key = 'your api key'
api_secret = 'your api secret'

To create a boy from python console try:
>>> from bot import *
>>> btc = Bot('BTCUSDT', '1h') 
>>> btc.open_socket()
>>> btc.get_historical()

Once you run get_historical your bot will now have pandas dataframe with historical data including SMA's 

                 open_time            open            high             low           close       volume           close_time  ... taker_base_vol  taker_quote_vol ignore         sma_5        sma_20        sma_50       sma_200

Once you run start() the bot will start pulling real time candle data from Binance. This is where buy/sell logic will go to make real time trading decisions.
In it's current state start() will just print the closed candle data to the console. 
