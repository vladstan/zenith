#Zenith - Portfolio Manager

This is probably the first portfolio manager developed for CLI. It is a portfolio manager with a twist because it is designed to have 1 reference coin (default and recommended in BTC), and track separately the accounts(cash) and the investment, trades in the coins. Of course, you can have multiple portfolios and everything is encrypted and stored only on your computer.

##Getting Started

You need to download this build and simply run zenith in your terminal. We have 3 versions for [Mac](https://s3-us-west-1.amazonaws.com/zenithportfolio.com/zenith-macos-x64), [Windows](https://s3-us-west-1.amazonaws.com/zenithportfolio.com/zenith-win-x86.exe) and [Linux 64](https://s3-us-west-1.amazonaws.com/zenithportfolio.com/zenith-linux-x64).

##Prerequisities

This product was build using node8.3 and Vorpal to create the command lines.

##Encryption

We are using [AES 256](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) to encrypt all the data from your portfolio. There is no cloud back-up so everything is stored on your computer on portfolios.dat To access the data from this file you need to have the password.

There is no cloud back-up for this, so please take care of your data because we can't send any backup.

##Getting started

The first command is the pass, so with this, you can create a password if you don't have one. After that, you need to create your first portfolio. You can use the default coin as a reference or any other coin you like. But you need to specify it.

```
pass
portfolio add Name BTC
```


Once the portfolio is created you need to deposit the budget allocated to invest/trade cryptocurrencies. The cash will be shown in Accounts.
Here is how you can deposit cash in your accounts.

[tx deposit BTC 12 "Details - received in mining"]
[tx deposit USD 25000 "Details - after I sold my apple stocks"]

These 2 transactions will deposit 12 BTC and 25k USD. The same is if you want to withdraw from your accounts.

```
tx withdraw BTC 1 "I wanted to buy a house"
```

You can see all the transactions in your account using this command

```
tx accounts
tx account BTC
```

The second one will show you only the transactions deposit/withdrawal on BTC

##Tracking the trades

we strongly recommend tracking the coins in accounts only in accounts and using the trading section only for the coins you want to trade. For example, I have 3 coins in accounts: EUR, BTC, and ETH that's because I usually move some money from my income in EUR, and I do mining for ETH and BTC.

We recommend using this money to trade other coins and of course calculate the profit in the reference coin.

Also, reference coin should be BTC, because only when people are going to use BTC as a unit of account will be considered money. We think we should be the first to use BTC as stored value, as a unit of trading but also as a unit of account.

To be able to track the portfolio you need to track all the transactions. We will build the portfolio for you composing all the transactions. Here is how you can add a transaction.

```
tx <buy/sell> <coin> <amount of coin> <price in BTC> <coin withdraw> <price in that coin>
tx buy LTC 85 0.01124 BTC 0.01124
```

In this transaction, we bought 85 LTC for 0.01124 BTC each. Second, we want to tell what account you want to withdraw the money spent on this transaction. If you don't specify it will not withdraw anything. You don't have to put the full amount paid for LTC but the price per coin.


Here is another example.

```
tx buy LTC 50 0.01122 EUR 44
```

we just bought 50 LTC for 0.01122 but because I bought them in EUR, I want to withdraw from my Eur account and I have to specify the price in EUR paid for each coin.


Just in case you made an error with any transactions you can delete. Here is how:


```
tx coins - this will list all the trades.
tx rm <id>
```

This will remove the transaction with the specified id obtain when you listed all the transactions.

##Portfolio Overview

There is only one command to have a portfolio overview.

```
overview
```

In this overview, you can see how much you paid in average per coin, how much it costs and how much is your total gain per coin. Also, we added how much the prices changed in the last 24h.



##Useful other commands.

To check a price for any coin in any other coin you can use

```
check price <coin> <coin>
check price BTC USD
```

##Versioning

We use SemVer for versioning. This is the version


##Licence

This project is licensed under the MIT License.


##Built with

* [NodeJS](https://nodejs.org/en/)
* [Vorpal](http://vorpal.js.org)


##Authors

* [Alexandru Rosianu](http://twitter.com/aluxian)
* [Vlad Stan](http://twitter.com/vladstan)

##Aknowledgements

Thank you [Edward](https://github.com/eduardbulai) for showing us your CLI portfolio manager.
