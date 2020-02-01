[![npm](https://img.shields.io/npm/v/mercadobitcoin-client-v3.svg)](https://www.npmjs.com/package/mercadobitcoin-client-v3)
[![GitHub issues](https://img.shields.io/github/issues/h3nr1ke/mercadobitcoin.svg)](https://github.com/h3nr1ke/mercadobitcoin/issues)
[![license](https://img.shields.io/github/license/h3nr1ke/mercadobitcoin.svg)](http://spdx.org/licenses/MIT)

# Mercado Bitcoin API client
[Mercado Bitcoin](https://www.mercadobitcoin.com.br) is a cryptocurrency exchange in Brazil. This module has been forked from [macmiranda's](https://github.com/macmiranda) module and modified to correct new format of open API while keeping the current functions.

## Install

```shell
npm install mercadobitcoin-client-v3
```

## Usage

There are 2 API endpoints. One for general info (public) and a trade API (require credentials)

### API - [documentation](https://www.mercadobitcoin.com.br/api-doc/)

```javascript
var MercadoBitcoin = require('mercadobitcoin-client-v3').MercadoBitcoin;

// The options for currency are: BTC, LTC, BCH, XRP and ETH
var mb = new MercadoBitcoin();

// Call ticker method to get last price of XRP
mb.get('ticker','XRP',console.log);

// Fetch the order book for BTC transactions (default)
mb.get('orderbook', null, console.log);
```

### TRADE API - [documentation](https://www.mercadobitcoin.com.br/trade-api)

Get your credentials at Mercado Bitcoin website

You will need the following info: Chave, Código ([here](https://www.mercadobitcoin.com.br/tapi/configuracoes/)). The PIN that was used in the previous versions is not needed anymore.

```javascript
var MercadoBitcoinTrade = require('mercadobitcoin-client-v3').MercadoBitcoinTrade;

// Credentials
var config = {  key    : 'xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx',
                secret : 'XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX',
};

var mbt = new MercadoBitcoinTrade(config);

// This object contains extra parameters that you might use for some methods:
var details = {
//		level: 'INFO' ,
		coin_pair: 'BRLXRP',
//		status_list: '[2,3]',
}

// Here you find some of the common methods that you can use as an example. For the complete list, please refer to the Trade API documentation: 
mbt.execute('get_account_info', null, console.log);
//mbt.execute('list_system_messages', details, console.log);
//mbt.execute('list_orders', details, console.log);
//mbt.execute('list_orderbook', details, console.log);

```

### Donations are welcome!
33c4WSnNiYj8thcmwxzhwPYTKsYt5YKeBa
