# topone-market-api
APIs for Market software, not for traders (用于行情软件，不用于交易者--数据延迟)

URL：http://market.top.one/


APIs:

1)The market list

Get /list

eg: http://market.top.one/list

Response：

      [{"market": "TOP/ETH",            #name
      "symbol_key": "TOP",              #symbol
      "symbol_name": "Top.One Coin",    #
      "anchor_key": "ETH",              #anchor
      "anchor_name": "Ethereum",        #
      "price": "0.00001238",            #last price
      "bidprice":"0.00001235",          #best buy price
      "askprice":"0.00001240",          #best sell price
      "24change": 0.027385892116182593, #24hours chang
      "24high": "0.00001352",           #24hours high
      "24low": "0.00001",               #24hours low
      "24volume": "26721502",           #24hours volume
      "24turnover": "305.04971772",     #24hours turnover
      "time": 1526131888}]              #time


2)Market depth data

Get /depth

eg: http://market.top.one/depth?market=TOP/ETH

Response：

      {"bids":
          [["0.00001199", "60822"],     #price, amount
           ["0.00001198", "10324"], 
           ["0.00001197", "29989"],
           ["0.00001196", "60974"], 
           ["0.00001189", "40796"], 
           ["0.00001186", "50000"],
           ["0.00001185", "84439"],
           ["0.00001183", "155663"],
           ["0.0000118", "169152"], 
           ["0.00001151", "50000"],
       "asks":
            [["0.00001237", "163538"], 
            ["0.00001238", "710802"], 
            ["0.00001239", "20000"], 
            ["0.00001245", "27502"],
            ["0.00001247", "48586"], 
            ["0.0000125", "432679"],
            ["0.0000126", "90000"],
            ["0.00001298", "236246"],
            ["0.00001299", "530000"], 
            ["0.000013", "81000"]], 
        "time": 1526133078.25686}

3)Market deals

Get /deals

eg: http://market.top.one/deals?market=TOP/ETH

Response：

      [[1526131288.302842, "0.00001238", "71782", "buy"],   #time, price, amount, buy/sell
      [1526131262.346612, "0.00001237", "9000", "buy"], 
      [1526131026.797729, "0.00001238", "565428", "buy"], 
      [1526130979.761151, "0.00001238", "324200", "buy"], 
      [1526130968.83686, "0.00001237", "3314636", "buy"],
      [1526130968.83671, "0.00001236", "200000", "buy"],
      [1526130968.836487, "0.00001236", "1000", "buy"],
      [1526129020.867658, "0.0000124", "28949", "sell"],
      [1526128700.599902, "0.0000124", "51537", "buy"], 
      ...]
