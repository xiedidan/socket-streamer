# socket-streamer
Grab data from Poloniex Push API, reconstruct orderbook in Redis.  
Subscribe to [Market Name] channel from Redis to get real-time orderbook snapshot with limited depth (defaults to 128).  
Subscribe to [Trade Channel] channel (defaults to poloniex_trade) to get trade info.
### Build and Start:
```
npm i
gulp build
node lib/async-streamer.js
```
### Start with PM2:
```
pm2 start lib/async-streamer.js
```
### Options:
```
  Usage: async-streamer [options]

  Options:

    -V, --version                   output the version number
    --redis-url <redisUrl>          Redis URL (default: redis://localhost:6379)
    --redis-prefix <redisPrefix>    Redis key prefix (default: orderbook)
    --trade-channel <tradeChannel>  Trade info Redis channel (default: poloniex_trade)
    --market <market>               Market list (default: BTC_ZEC,BTC_ETH,ETH_ZEC)
    -h, --help                      output usage information
```
