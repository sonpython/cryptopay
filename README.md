# Description
Open source Crypto QR code standard (OCQR) for payment between issuers and payers.
You can add any cryptocurrency as you want to accept and generate OCQR yourself.
Any one could be a Cryptocurrencies accepted merchant.

# Workflow

![OCQR workflow](https://raw.githubusercontent.com/sonpython/cryptopay/master/OCQR_workflow.svg)

# Todo
- Create/connect with 3rd parties to get exchange rate between cryptocurrencies
- Make Merchant OCQR generation Web UI
- Make Merchant OCQR generation API endpoint
- Make Mobile application for crypto accepted merchants to generate OCQR
- Make Mobile application for user to pay with their crypto wallet (add wallet, scan OCQR, fingerprint authorize, payment history)
- Make a payment gateway standard to integrate to 3rd POS, CRM, ERP, Online Cart Softwares...

# Format
### Minimal format
```
{
  "merchant": "Dropdeck shop",
  "payment": [
    {
      "code": "ETH",
      "amount": 0.4028,
      "address": "0xFD4B7Ad5768E766d3BFe064c49a8135344b5ee73"
    },
    {
      "code": "BTC",
      "amount": 0.0335,
      "address": "1NHBhymHokdF499oMRyEPSfvU8HtEgRnEV"
    },
    {
      "code": "DDT",
      "amount": 2000,
      "address": "0xFD4B7Ad5768E766d3BFe064c49a8135344b5ee73"
    }
  ]
}
```
Minimal minimized format (To optimize QR code size)
```
{"merchant":"Dropdeck shop","payment":[{"code":"ETH","amount":0.4028,"address":"0xFD4B7Ad5768E766d3BFe064c49a8135344b5ee73"},{"code":"BTC","amount":0.0335,"address":"1NHBhymHokdF499oMRyEPSfvU8HtEgRnEV"},{"code":"DDT","amount":2000,"address":"0xFD4B7Ad5768E766d3BFe064c49a8135344b5ee73"}]}
```
OCQR code for minimal version example
![OCQR code for minimal version example](https://raw.githubusercontent.com/sonpython/cryptopay/master/minimal_qr_code.jpg)

### Standard format

```
{
  "merchant": "Dropdeck shop",
  "address": "123 Singapore",
  "items": [
    {
      "name": "Premium package",
      "description": "Premium package for 1 year",
      "payment": [
        {
          "code": "ETH",
          "amount": 0.2014,
          "name": "Ether"
        },
        {
          "code": "BTC",
          "amount": 0.01675,
          "name": "Bitcoin"
        },
        {
          "code": "DDT",
          "amount": 1000,
          "name": "Dropdeck coin"
        }
      ]
    },
    {
      "name": "Startup on block chain",
      "description": "Push startup info to block chain service",
      "payment": [
        {
          "code": "ETH",
          "name": "Ether",
          "amount": 0.2014
        },
        {
          "code": "BTC",
          "name": "Bitcoin",
          "amount": 0.01675
        },
        {
          "code": "DDT",
          "name": "Dropdeck coin",
          "amount": 1000
        }
      ]
    }
  ],
  "invoice": 123456,
  "created": "2017-07-23T18:25:43.511Z",
  "payment": [
    {
      "code": "ETH",
      "name": "Ether",
      "amount": 0.4028,
      "address": "0xFD4B7Ad5768E766d3BFe064c49a8135344b5ee73"
    },
    {
      "code": "BTC",
      "name": "Bitcoin",
      "amount": 0.0335,
      "address": "1NHBhymHokdF499oMRyEPSfvU8HtEgRnEV"
    },
    {
      "code": "DDT",
      "name": "Dropdeck coin",
      "amount": 2000,
      "address": "0xFD4B7Ad5768E766d3BFe064c49a8135344b5ee73"
    }
  ]
}
```

Standar minimized format (To optimize QR code size)

```
"merchant":"Dropdeck shop","address":"123 Singapore","items":[{"name":"Premium package","description":"Premium package for 1 year","payment":[{"code":"ETH","amount":0.2014,"name":"Ether"},{"code":"BTC","amount":0.01675,"name":"Bitcoin"},{"code":"DDT","amount":1000,"name":"Dropdeck coin"}]},{"name":"Startup on block chain","description":"Push startup info to block chain service","payment":[{"code":"ETH","name":"Ether","amount":0.2014},{"code":"BTC","name":"Bitcoin","amount":0.01675},{"code":"DDT","name":"Dropdeck coin","amount":1000}]}],"invoice":123456,"created":"2017-07-23T18:25:43.511Z","payment":[{"code":"ETH","name":"Ether","amount":0.4028,"address":"0xFD4B7Ad5768E766d3BFe064c49a8135344b5ee73"},{"code":"BTC","name":"Bitcoin","amount":0.0335,"address":"1NHBhymHokdF499oMRyEPSfvU8HtEgRnEV"},{"code":"DDT","name":"Dropdeck coin","amount":2000,"address":"0xFD4B7Ad5768E766d3BFe064c49a8135344b5ee73"}]}
```
OCQR code for standard version example
![OCQR code for standard version example](https://raw.githubusercontent.com/sonpython/cryptopay/master/standard_qr_code.jpg)