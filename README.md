# Prop Firm Edge mt5

This code is a sample Expert Advisor (EA) for the MetaTrader 5 (MT5) platform, which is designed to trade in the foreign exchange (forex) market. It utilizes the Relative Strength Index (RSI) indicator to generate buy and sell signals based on predefined levels. The EA also includes account limit management features to control risk.

## RSI Indicator Parameters

- `RSI_Period` (default: 14): The period for calculating the RSI value.
- `Overbought_Level` (default: 70): The threshold level for identifying overbought conditions based on RSI.
- `Oversold_Level` (default: 30): The threshold level for identifying oversold conditions based on RSI.

## Entry Position Parameters

- `Buy_RSI_Level` (default: 40): The RSI level at which a buy signal is generated.
- `Sell_RSI_Level` (default: 60): The RSI level at which a sell signal is generated.

## Account Limit Management Parameters

- `Max_Drawdown_Limit` (default: 0.05): The maximum allowed drawdown limit for the trading account.

## Custom Indicator - RSI

The `RSI` function calculates the RSI value based on the specified period. It uses the built-in `iRSI` function of MQL5, which requires the symbol, timeframe, period, applied price, and shift as parameters.

## Expert Initialization Function

The `OnInit` function is called when the EA is initialized. It initializes necessary variables and indicators. In this sample code, it returns `INIT_SUCCEEDED` to indicate successful initialization.

## Expert Tick Function

The `OnTick` function is called on each tick of the price data. It calculates the RSI value using the `RSI` function and checks for buy and sell signals based on the predefined RSI levels.

If the RSI value is below the `Buy_RSI_Level`, a buy order is placed with a lot size calculated as 1% of the account balance. Similarly, if the RSI value is above the `Sell_RSI_Level`, a sell order is placed.

The function also checks for high volatility and news releases using the `IsHighVolatility` and `IsNewsRelease` functions. If the account drawdown exceeds the `Max_Drawdown_Limit`, the trading parameters are adjusted to manage risk. The actual actions for risk management and trading decisions based on the RSI indicator are not included in this code.

## Check if Market is Experiencing High Volatility

The `IsHighVolatility` function checks if the market is experiencing high volatility based on market fluctuations. The actual logic for determining high volatility is not included in this code, and it currently returns `true` as a placeholder.

## Check if There is a News Release

The `IsNewsRelease` function checks if there is a news release that may impact market fluctuations. The actual logic for identifying news events and their impact is not included in this code, and it currently returns `true` as a placeholder.

## Expert Deinitialization Function

The `OnDeinit` function is called when the EA is deinitialized or shut down. It is used to clean up and perform necessary actions before shutting down.

Please note that ForexRobotEasy is not the official developer of this product. This code is provided as a sample that can work based on the description of the product. To find the official developer of this product, please refer to MQL5.

For detailed reviews and trading results of this product, please visit [Forex Robot Easy](https://forexroboteasy.com/forex-robot-review/prop-firm-edge-mt5-review-mastering-forex-trading-with-rsi/) website.
