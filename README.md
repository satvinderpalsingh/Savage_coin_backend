# Savage_coin_backend
Simple blockchain based cryptocurrency name Savage Coin
# Features
 -Simple proof-of-work algorithm<br/>
-Verify blockchain (to prevent tampering)<br/>
-Generate wallet (private/public key)<br/>
-Sign transactions<br/>
-Generate Key Pairs<br/>

# Installation
npm i savage_coin
//execute above command to insatll blockchain as npm module and use it with project

# Generate Key Pairs
To make transactions on this blockchain we need a keypair. The public key becomes our wallet address, the private key is used to sign transactions and also public key is used to verify the transactions

```
const EC = require('elliptic').ec;
const ec = new EC('secp256k1');

const myKey = ec.genKeyPair();
//myKey consist of public key  and private key can we extracted using myKey.getPublic('hex') and myKey.getPrivate('hex') resp. in hexadecimal format
```

#getting started with Blockchain
 
```
 const Satvinder = new Blockchain()
```

## Add transactions
```
// Transfer 100 coins from my wallet to "toAddress"
const tx = new Transaction(myKey.getPublic('hex'), 'toAddress', 100);
tx.signTransaction(myKey);//signing the transaction for verification

Satvinder.addTransaction(tx);
```
 ##To finalize the above  transaction, we need to mine a new block. We give this method our wallet address because we will receive a mining reward also:
 ```Satvinder.minePendingTransactions(myKey.getPublic('hex'));```


