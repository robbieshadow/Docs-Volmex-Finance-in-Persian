# دسترسی به API

ای پی آی volmex.finance API با شاخص قیمت گذاری در زیر موجود است.                                                        &#x20;

{% embed url="https://api.volmex.finance/graphql" %}

کوئری زیر را می توان برای استخراج شاخص نوسانات، دارایی، قیمت کالای اساسی و مهر زمانی یونیکس استفاده کرد. دارایی را برای مشاهده شاخص های مربوطه تغییر دهید.                                                                                      &#x20;

```
query impliedVol {
  impliedVolatilitys(limit:10, offset: 0, query: {
    asset: ETH
  }, sort: "-timestamp") {
    index
    asset
    timestamp
    underlying_index
  }
}
```

نمونه خروجی از query بالا:                                                                                                                                &#x20;

```
{
  "data": {
    "impliedVolatilitys": [
      {
        "index": 1.1205327814475294,
        "underlying_index": 2597.08,
        "epoch": 3714,
        "timestamp": 1623729904000
      },
      {
        "index": 1.1188762043011018,
        "underlying_index": 2590.94,
        "epoch": 3713,
        "timestamp": 1623729605000
      },
      {
        "index": 1.1204085089104692,
        "underlying_index": 2592.38,
        "epoch": 3712,
        "timestamp": 1623729304000
      },
      {
        "index": 1.1235643093126018,
        "underlying_index": 2592.72,
        "epoch": 3711,
        "timestamp": 1623729004000
      },
      {
        "index": 1.1215874384348783,
        "underlying_index": 2590.78,
        "epoch": 3710,
        "timestamp": 1623728703000
      },
      {
        "index": 1.1208957517316536,
        "underlying_index": 2590.25,
        "epoch": 3709,
        "timestamp": 1623728406000
      },
      {
        "index": 1.1218123854425053,
        "underlying_index": 2592.5,
        "epoch": 3708,
        "timestamp": 1623728104000
      },
      {
        "index": 1.1223732562551632,
        "underlying_index": 2587.67,
        "epoch": 3707,
        "timestamp": 1623727805000
      },
      {
        "index": 1.123005210822689,
        "underlying_index": 2587.81,
        "epoch": 3706,
        "timestamp": 1623727504000
      },
      {
        "index": 1.1218374602435601,
        "underlying_index": 2586.45,
        "epoch": 3705,
        "timestamp": 1623727204000
      }
    ]
  }
}
```

کوئری زیر را می توان با Volmex API استفاده کرد تا مشخص شود شاخص در حال حاضر به کدام گزینه اشاره می کند.                                                                                                                                                            &#x20;

```
query getImpliedVolatility {
  impliedVolatilitys(limit:101, offset: 0, query: {
    asset: ETH
  }, sort: "-epoch") {
    index
    underlying_index
    epoch
    asset
    linkedOrderBooks {
      underlying_index
      underlying_price
      instrument_name
      mid_price
    }
  }
}
```

نمونه خروجی از query بالا:                                                                                                                                &#x20;

```
{
  "data": {
    "impliedVolatilitys": [
      {
        "index": 1.2048225385936862,
        "underlying_index": 2440.33,
        "epoch": 2550,
        "asset": "ETH",
        "linkedOrderBooks": [
          {
            "underlying_index": "ETH-25JUN21",
            "underlying_price": 2423.65,
            "instrument_name": "ETH-25JUN21-2400-C",
            "mid_price": 0.09425
          },
          {
            "underlying_index": "ETH-25JUN21",
            "underlying_price": 2423.65,
            "instrument_name": "ETH-25JUN21-2400-P",
            "mid_price": 0.084
          },
          {
            "underlying_index": "ETH-25JUN21",
            "underlying_price": 2423.65,
            "instrument_name": "ETH-25JUN21-2560-C",
            "mid_price": 0.06425
          },
          {
            "underlying_index": "ETH-25JUN21",
            "underlying_price": 2423.65,
            "instrument_name": "ETH-25JUN21-2560-P",
            "mid_price": 0.12175
          },
          {
            "underlying_index": "ETH-30JUL21",
            "underlying_price": 2440.4,
            "instrument_name": "ETH-30JUL21-2400-P",
            "mid_price": 0.164
          },
          {
            "underlying_index": "ETH-30JUL21",
            "underlying_price": 2440.4,
            "instrument_name": "ETH-30JUL21-2400-C",
            "mid_price": 0.17975
          },
          {
            "underlying_index": "ETH-30JUL21",
            "underlying_price": 2440.4,
            "instrument_name": "ETH-30JUL21-2500-P",
            "mid_price": 0.187
          },
          {
            "underlying_index": "ETH-30JUL21",
            "underlying_price": 2440.4,
            "instrument_name": "ETH-30JUL21-2500-C",
            "mid_price": 0.1625
          }
        ]
```
