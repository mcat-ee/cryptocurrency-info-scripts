import requests
import json
import time

# urls
independent_reserve_url = "https://api.independentreserve.com/Public/GetMarketSummary?primaryCurrencyCode=eth&secondaryCurrencyCode=aud"
acx_url = "https://acx.io//api/v2/tickers/ethaud.json"
btcm_url = "https://api.btcmarkets.net/market/ETH/AUD/tick"
coinspot_url = "https://www.coinspot.com.au/sell/eth/rate/aud"#"https://www.coinspot.com.au/sell/eth"
coinbase_url = "https://api.coinbase.com/v2/exchange-rates?currency=ETH"

def get_independent_reserve_price():
	response = requests.get(independent_reserve_url)
	obj = json.loads(response.text)
	print "\tIndependent Reserve\n\t\t", obj['CurrentHighestBidPrice']

def get_acx_price():
	response = requests.get(acx_url)
	obj = json.loads(response.text)
	print "\tACX\n\t\t", obj['ticker']['sell']

def get_btc_markets_price():
	response = requests.get(btcm_url)
	obj = json.loads(response.text)
	print "\tBTCM\n\t\t", obj['lastPrice']


def get_coinspot_price():
	#	Response includes a display rate and a normal rate, worth noting
	response = requests.get(coinspot_url)
	obj = json.loads(response.text)
	print "\tCoinspot\n\t\t", obj['displayrate']


def get_coinbase_price():
	response = requests.get(coinbase_url)
	obj = json.loads(response.text)
	print "\tCoinbase\n\t\t", obj['data']['rates']['AUD']

def get_sell_prices():
	print "SELL PRICES"
	get_coinbase_price()

	get_coinspot_price()

	get_independent_reserve_price()

	get_acx_price()

	get_btc_markets_price()
	
if __name__ == "__main__":
	print time.strftime("%H:%M:%S")
	get_sell_prices()
