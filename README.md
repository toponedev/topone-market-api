# topone-market-api
Official Documentation for the market APIs

TOP.ONE 对外行情接口说明

请求交互

REST访问的根URL：http://market.top.one/


API参考

1)获取交易所交易列表及24小时涨跌统计

Get /list

URL http://market.top.one/list

Response示例：

      [{"market": "TOP/ETH",            #名称
      "symbol_key": "TOP",              #标的
      "symbol_name": "Top.One Coin",    #标的全称
      "anchor_key": "ETH",              #报价标的
      "anchor_name": "Ethereum",        #报价标的全称 
      "price": "0.00001238",            #最新价格
      "24change": 0.027385892116182593, #24小时涨跌  
      "24high": "0.00001352",           #24小时最高价
      "24low": "0.00001",               #24小时最低价
      "24volume": "26721502",           #24小时成交量
      "24turnover": "305.04971772",     #24小时成交额 
      "time": 1526131888}]              #时间


2)获取交易深度数据

Get /depth

URL http://market.top.one/depth?market=TOP/ETH

Response示例：

      {"bids":
          [["0.00001199", "60822"],     #价格，数量
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

3)获取交易成交数据

Get /deals

URL http://market.top.one/deals?market=TOP/ETH

Response示例：

      [[1526131288.302842, "0.00001238", "71782", "buy"],   #时间，价格，数量，买卖
      [1526131262.346612, "0.00001237", "9000", "buy"], 
      [1526131026.797729, "0.00001238", "565428", "buy"], 
      [1526130979.761151, "0.00001238", "324200", "buy"], 
      [1526130968.83686, "0.00001237", "3314636", "buy"],
      [1526130968.83671, "0.00001236", "200000", "buy"],
      [1526130968.836487, "0.00001236", "1000", "buy"],
      [1526129020.867658, "0.0000124", "28949", "sell"],
      [1526128700.599902, "0.0000124", "51537", "buy"], 
      ...]
