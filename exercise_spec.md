# Blockchain and Big Data, 2016/11/06 

### Exercise #1

## Introduction
In this exercise, we will write a simple program to do some operations on Gcoin blockchain via DiQi API. In our design, user private keys would be owned by themselves instead of Gcoin core. Therefore, you would need to use `pygcointools` to sign a transaction offline. 

### What is Gcoin
Gcoin is a blockchain protocol which is derived from Bitcoin with some additional features. One significant difference between Gcoin and Bitcoin is that Gcoin is a multi-currency blockchain. In Gcoin, you can create a new 'license' representing a new type of currency. Each license is associated with an Gcoin address, so the owner of the address has the power to control the amount of the currency circulating in the Gcoin blockchain. To increase the total amount of a currency, the owner will simply 'mint' more currency and distribute it to the blockchain. 

If you are interested in Gcoin, [here](https://github.com/OpenNetworking/gcoin-community) is the source code.

### What is DiQi API
DiQi API is a wrapper of Gcoin core. There are some restful APIs for you to communicate with Gcoin core easily. For more information of DiQi API, please refer to the other document.

### What is pygcointools
[pygcointools](https://pypi.python.org/pypi/gcoin/1.1.44) is a Python library for Gcoin signatures and transactions. It's extended from `pybitcointools` you used in howework #1. You can install the library via pip. In this howework, you will use `pygcointools` to create an address like you did in howework #1. In addition, you will need to use it to sign a raw transaction.

## Problem
1. Generate an address: Use pygcointools to generate your private key and your address by your national ID.
2. Issue a new license: Use your last six digital part of national ID as your license color id to create your own license.
3. Mint your license: There are three steps in this procedure. You should create a mint raw transaction first. Then, use pygcointools to sign the raw transaction. Finally, broadcast the transaction to the Gcoin network.
4. Retrieve the fee: Due to Gcoin transaction fee mechanism, you should get some transaction fee before you create a payment.
5. Create a payment: This procedure is similar to the previous one. You should send some of your license you just created to TA's address (`13zYswW4SV31SynXXM8dwEkyMnu5A2XUmJ`). You still need to create a raw transaction, sign it locally, and then broadcast it to the network.

You could get address balance via DiQi API to see if you send money to TA's address successfully.

