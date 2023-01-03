
# all/{currency}
---
Returns current Bitcoin conversion rates in selected currency from the following sites: Blockchain, Bitfinex, Bitcoincharts, Coinbase, and Bitpay.


## GET https://community-bitcointy.p.mashape.com/all/{currency}

---
   

|  Parameter | Required | Description | Type |  
|------------|----------|-------------|------|
| {currency}  | YES  |  Target currency for bitcoin conversion. Use ISO three letter abberviations. All major currencies supported. Other currency support depends on the exchange queried. | string

---

## Sample Request

A cURL `GET` AJAX request for exchange rates in USD:


```
curl --get --include 'https://community-bitcointy.p.mashape.com/all/USD' \
  -H 'X-Mashape-Key: <APIKEY>'
  -H 'Accept: text/plain'
```

The `--get` flag sets the HTTP method to `GET`, while the `--include` flag tells the server to include the HTTP response headers in the output. Replace `<APIKEY>` with valid Mashape key in the first header `-H` and set `Accept` to `text/plain` in the second header `-H`.
    
## Sample Response

The following array of objects is an example of the JSON response for exchange rate in USD:

```json
[
  {
    "exchange": "blockchain",
    "currency": "USD".
    "value" 3999.94
  },
   {
    "exchange": "blockchain",
    "currency": "USD".
    "value" 3999.94
  },
   {
    "exchange": "blockchain",
    "currency": "USD".
    "value" 3999.94
  },
   {
    "exchange": "blockchain",
    "currency": "USD".
    "value" 3999.94
  },
   {
    "exchange": "blockchain",
    "currency": "USD".
    "value" 3999.94
  }
]
```


|  Property | Description  |  
|-----------|--------------|
| exchange  |  The exchange site: Blockchain, Bitfinex, Btccharts, Coinbase, or Bitpay. | 
| currency  |  The type of currency selected to be converted into from Bitcoin. All major currencies are supported in ISO three digit abbrevia- tions. Several other currencies are supported, depending on the exchange server selected. If an exchange does not accept the cur- rency type selected, the value of value is false. Except for bitpay, which returns `0` when the selected currency is unsupported. |
| value  |  The current value of bitcoin converted into the selected currency. |  

---  
### Sample Implementation

The following HTML/JavaScript code sample shows how to call the `all/{currency}` endpoint to get the conversion rate of a specific currency from each of the five supported bitcoin exchanges as shown in the Sample Response above.

```html
<html>
  <head>
    <script src="http://code.jquery.com/jquery-3.3.1.min.js"></script>
    <script>

      var settings = {
        "async": true,
        "crossDomain": true,
        "url": "https://community-bitcointy.p.mashape.com/all/EUR",
        "method": "GET"
        "headers": {
          "x-mashape-key": "<APIKEY>",
          "accept": "text/plain",
        }
      }

      $.ajax(settings).done(function (response) {
        console.log(response);
        $("convertblckchn").append(response[0].value);
      });

    </script>
  </head>
  <body>
    <h2>Current Bitcoin Conversion Rate in EUR froom Blockchain</h2>
    <div id="convertblckchn"></div>
  </body>
</html>
```

In this example, the [jQuery’s](https://jquery.com/) `ajax()` method requests the remote resource asynchro- nously. Authorization gets passed through the header rather than in the endpoint path. Enter a valid API key as the value of “x-mashape-key” instead of “<APIKEY>”, as shown here.

Here, the `done()` method handles the response from the server request by first logging the entire AJAX response object to the console and then appending the value of the first item of the response (i.e. `response[0]`) to the HTML span element with `id` `convertblckchn`. The value is then rendered as a child of that element in the browser’s DOM to see.
