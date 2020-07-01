# API-Documentation
Welcome to the Bitcoiva Market REST API documentation. This API (Application Programming Interface) will allow you to access the functionality of this exchange by means of HTTP requests, making integration with your own applications possible.

Usage :
In order to use a public API method, you must make an HTTP request to the appropriate endpoint for that particular method, sending the appropriate GET or POST parameters for that method. You can also send them in the PAYLOAD of the request in JSON format.

Public API Methods :
These methods can be accessed without an account or API key.

# Tickers:
 
Link : GET https://bitcoiva.com/api/tickers
 
Response :
{
    "status": 1,
    "pairlist": [
        {
            "pair": "BTC_USDT",
            "minAmount": "0.00274494",
            "minPrice": "0.00200000",
            "lastPrice": "9145.97000000",
            "maker": "0.00",
            "taker": "0.00"
        },
}

# Pair Details:

Link : POST https://bitcoiva.com/api/pairDetails

Params : pair(BTC_USDT)

Response : 

{
    "status": 1,
    "message": "suceess",
    "pair": "BTC_USDT",
    "minAmount": "0.00274494",
    "minPrice": "0.00200000",
    "lastPrice": "9140.00000000",
    "maker": "0.25",
    "taker": "0.25"
}

# Buy Orders:

Link : POST https://bitcoiva.com/api/getOrders

Params : type(Buy), pair(BTC_USDT)

Response : 

{
	"status": 1,
	"message": "suceess",
	"orders": [
		{
			"amount": "3.00000000",
			"price": "3.00000000"
		}
	]
}

# Sell Orders :

Link :POST https://bitcoiva.com/api/getOrders
 
Params : type(Sell), pair(BTC_USDT)

Response : 

{
	"status": 1,
	"message": "suceess",
	"orders": [
		{
			"amount": "3.00000000",
			"price": "3.00000000"
		}
	]
}

# Market History :

Link : POST https://bitcoiva.com/api/getHistory

Params : pair(BTC_USDT)

Response : 

{
	"status": 1,
	"message": "suceess",
	"orders": [
		{
		"datetime": "17:08:58",
		"amount": "3.00000000",
		"price": "3.00000000"
		}
	]
}

Private API Methods : 
These methods cannot be accessed without an account or API key and secret key, Needed parameters(api_key,api_secret).

#  Open Orders 

Link : POST https://bitcoiva.com/api/getActiveOrders

Params : api_key, api_secret, pair(BTC_USDT)

Response :

{
	"status": 1,
	"message": "suceess",
	"orders": [
	{
		"datetime": "2020-06-27 16:24:23",
		"type": "Buy",
		"amount": "3.00000000",
		"price": "3.00000000",
		"total": "9.00000000",
		"orderid": "VGx6NnhMSDFkUmxnU2ZTc0FqMDdUZz09"
		}
	]
}

#  Stop Orders 

Link : POST https://bitcoiva.com/api/getStopOrders

Params : api_key, api_secret, pair(BTC_USDT)

Response :

{
	"status": 1,
	"message": "suceess",
	"orders": [
		{
		"datetime": "2020-06-27 16:25:09",
		"type": "Buy",
		"amount": "3.00000000",
		"price": "4.00000000",
		"total": "12.00000000",
		"orderid": "ZG1XWU9KNU05UitDQVZNMzBlckhhdz09"
		}
	]
}

# My Trade History 

Link : POST https://bitcoiva.com/api/getMyhistory

Params : api_key, api_secret, pair(BTC_USDT)

Response : 

{
	"status": 1,
	"message": "suceess",
	"orders": [
		{
			"datetime": "2020-06-27 17:08:58",
			"type": "Buy",
			"amount": "3.00000000",
			"price": "3.00000000",
			"total": "9.00000000",
			"fees": "0.00750000 BTC",
			"status": "Filled"
		}
	]
}

# Create Order 

Link : POST https://bitcoiva.com/api/createOrder

Params : api_key, api_secret, order, amount, price, pair(BTC_USDT), type(Buy/Sell)

Response : 

{
	"status": "1",
	"message": "Buy/Sell Order Placed Successfully"
}


# Cancel Order 

Link : POST https://bitcoiva.com/api/cancelOrder

Params : api_key, api_secret, orderid

Response : 

{
	"status": "1",
	"message": "Order cancelled successfully"
}


You are permited to make up to 20 requests a minute.




