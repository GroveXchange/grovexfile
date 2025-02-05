CoinGecko API Integration

Endpoint 1 - **/tickers**（Market Information）

Endpoint：/pub/tickers

Full url：https://openapi.grovex.io/pub/tickers

Request Method：GET

Request Parameters：

| Name     | Type  | Status | Description                                                    |
| --------- | ------ | ---- | --------------------------------------------------------- |
| ticker_id | string | Must-fill | Trade pair identifiers, such as BTC_ETH, using separators between underlying and target assets |

Response Description：

| Name            | Data Type | Description                                                         |
| --------------- | -------- | ------------------------------------------------------------ |
| ticker_id       | string   | rade pair identifiers, such as BTC_ETH, using separators between underlying and target assets（DEX will use contract address） |
| base_currency   | string   | Symbol/currency code/contract address of the underlying crypto                    |
| target_currency | string   | Symbol/currency code/contract address of the target crypto                     |
| last_price      | decimal  | Latest transaction price of the underlying asset based on the target asset                         |
| base_volume     | decimal  | 24-Hour Volume of Trading Pairs (Based Assets)                       |
| target_volume   | decimal  | 24-hour volume of trading pairs (Unit:  target assets)                       |



Endpoint 2 - **/orderbook**（Order Book Depth Details）

Endpoint：/pub/newOrderBook

Full url：https://openapi.grovex.io/pub/newOrderBook

Example url：https://openapi.grovex.io/pub/newOrderBook?symbol=btcusdt&depth=100

Request Method：GET

Request Parameters：

| Name     | Type  | Status | Description                                                    |
| --------- | ------ | ---- | --------------------------------------------------------- |
| symbol | string  | Must-fill | Trading pair identifiers such as btcusdt, lowercase                               |
| depth  | integer | optional | Order book depth quantity: [0, 100, 200] .0 Return full depth. Depth = 100 means 50 on each side of the orderbook. Not fill in default to 0 |

**Response Description：**

| Name            | Data Type | Description                                            |
| ---- | -------- | ---------------------------------------------- |
| bids | decimal  | An array of two elements for each bid price and quantity |
| asks | decimal  | An array of two elements for each ask price and quantity |