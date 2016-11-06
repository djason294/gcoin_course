# Document
## DiQi API
DiQi API is a middleware that allows you to communicate with Gcoin blockchain easily. You would need to use DiQi API to accomplish this exercise. For example, calling `base/v1/transaction/send` to broadcast the transaction.

As you know, blockchain consists of many blocks chained one by one and each block contains many transactions. In Gcoin, ther are several transaction types including normal payments, license type, mint type, etc. No matter what type of a transaction it is, three things has to be done before sending the transaction to Gcoin network. First, a raw transaction, which is an unsigned transaction containing transaction inputs and outputs, has to be created. Second, the raw transaction has to be signed. Finally, the signed transaction can be broadcasted through the DiQi API.

Signing a transaction could be done in both offline or calling `signrawtransaction` RPC. However, we would focus on signing transactions offline in this exercise design because we want the blockchain has nothing to do with user private keys. Therfore, signing a transaction doesn't need to call DiQi API. Instead, you should use `pygcointools` library to achieve this.

* DiQi API base URL: `http://52.198.247.0:8000/`
* TA's address: `13zYswW4SV31SynXXM8dwEkyMnu5A2XUmJ`

### Get address balance
You can get the balance of an address by calling this API. After you broadcast the transaction, you can check if it is in TA's address by calling this API. If it is, your exercise is complete.
> HTTP request

GET `base/v1/balance/<address>`
> Arguments

None
> Sample response

```
{
    "1": "10.00000000",
    "249166": "16800.00000000"
}
```

### Get license info
You can get the license info by calling this API. You can use this API to check if you create your license successfully.
> HTTP request

GET `base/v1/license/<color_id>`
> Arguments

None
> Sample response

```
{
    "member_control": false,
    "metadata_hash": "0000000000000000000000000000000000000000000000000000000000000000",
    "name": "戴睿頡",
    "upper_limit": 0,
    "mint_schedule": "free",
    "description": "TA",
    "fee_rate": "0E-8",
    "metadata_link": "www.example.com",
    "fee_type": "fixed",
    "total_amount": 16800,
    "version": 1,
    "owner": "13zYswW4SV31SynXXM8dwEkyMnu5A2XUmJ",
    "fee_collector": "none",
    "divisibility": true,
    "issuer": "none"
}
```

### Create a new license
You can create your license from this API. Every license has an unique color ID. In this howework, `color_id` should be the last six digit part of your national ID. For example, if your national ID is A123456789, then the `color_id` should be 456789. If your number is taken by someone else, choose a random number between 10000 to 99999. Beware that once a license is created, the license info can't be modified.

If nothing goes wrong, you will get the `tx_id` response which means you have sucessfully created your license. Last, you wouldn't need to sign this transaction anymore. This API has taken care of all three steps due to a complicated issue.
> HTTP request

GET `base/v1/license/prepare`
> Arguments

Argument  | Type  | Description
----------|-------|------------
color_id  | int   | your national ID
address   | string| your address
name      | string| your real name, in Mandarin or English
description| string| your department

> Sample response

```
{
    "tx_id": "a9ee32b367754a0bd8aa5ace43a55d734a968f0e15bb602ad865ca9b35473ae2"
}
```

### Mint your license
You can mint your license by calling this API. This API would return a raw transaction which you need to sign later.
> HTTP request

GET `base/v1/mint/prepare`
> Arguments

Argument    | Type  | Description
------------|-------|------------
mint_address| string| your address
color_id    | int   | your license color ID
amount      | float | amount
> Sample response

```
{
    "raw_tx": "01000000010000000000000000000000000000000000000000000000000000000000000000ffffffff1976a9140c0a86d78bc3f71db1f969353da4769e2084bc5988acffffffff0100ca9a3b000000001976a9140c0a86d78bc3f71db1f969353da4769e2084bc5988ac010000000000000001000000"
}
```

### Create a payment
You can send money to TA's address by calling this API. This API would return a raw transaction which you need to sign later.
> HTTP request

GET `base/v1/transaction/prepare`
> Arguments

Argument    | Type  | Description
------------|-------|------------
from_address| string| your address
to_address  | string| TA's address
color_id    | int   | any license color ID you have
amount      | float | amount
> Sample response

```
{
    "raw_tx": "01000000010000000000000000000000000000000000000000000000000000000000000000ffffffff1976a9140c0a86d78bc3f71db1f969353da4769e2084bc5988acffffffff0100ca9a3b000000001976a9140c0a86d78bc3f71db1f969353da4769e2084bc5988ac010000000000000001000000"
}
```

### Broadcast the transaction
You can broadcast the transaction to the Gcoin network by calling this API.
> HTTP request

POST `base/v1/transaction/send`
> Arguments

Argument | Type  | Description
---------|-------|------------
raw_tx   | string| the signed transaction
> Sample response

```
{
    "tx_id": "3e329de5b87f85a45d3096d14f00e461523069310134e91d1e0e17275ed5c084"
}
```

### Get transaction fee
This API is a kind of backdoor that simplify the exercise. Because Gcoin has fee mechanism, every payment (normal transaction) would consume one DiQi coin (transaction fee). You could call this API with given address to get 10 transaction fee before you want to create a payment. This API could be called again if you ran out of your transaction fee.
> HTTP request

POST `base/v1/fee/<address>`
> Arguments

None
> Sample response

```
{
    "tx_id": "3e329de5b87f85a45d3096d14f00e461523069310134e91d1e0e17275ed5c084"
}
```

## pygcointools
pygcointools is a Python library that handles signatures and transactions. Signing a transaction with your private key is like you confirm this transaction. If you signed the transaction with a wrong key, which means the transaction was not belonged to you, it would be denied by the network.

You could install pygcointools on python 2 by `pip install gcoin` .

```
> from gcoin import *
> priv = sha256("<your national ID>")
> addr = privkey_to_address(priv)
> print('addr: '+ addr)
> #to sign the raw transaction
> raw_tx = "<raw_tx>"
> signed_tx = signall(raw_tx, priv)
> print('signed_tx: '+ signed_tx)
```
