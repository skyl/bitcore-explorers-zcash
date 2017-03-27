# Explorers
The `bitcore-explorers-zcash` module provides a convenient interface to retrieve unspent transaction outputs and broadcast transactions to the Zcash network via blockchain explorers.

## Installation (TODO)
Explorers is implemented as a separate module.

For node projects:

```
npm install bitcore-explorers-zcash --save
```

For client-side projects:

```
bower install bitcore-explorers-zcash --save
```

## Insight
### Description
`Insight` is a simple agent to perform queries to an Insight blockchain explorer. The default server is: https://explorer.testnet.z.cash/. Run your own server: https://github.com/str4d/insight-api-zcash.

There are currently two methods implemented: `getUnspentUtxos` and `broadcast`. The API will grow as features are requested.

#### Retrieving Unspent UTXOs for an Address (or set of)

```javascript
var Insight = require('bitcore-explorers-zcash').Insight;
var insight = new Insight();

insight.getUnspentUtxos('1Bitcoin...', function(err, utxos) {
  if (err) {
    // Handle errors...
  } else {
    // Maybe use the UTXOs to create a transaction
  }
});
```

#### Broadcasting a Transaction

```javascript
var insight = new Insight();
insight.broadcast(tx, function(err, returnedTxId) {
  if (err) {
    // Handle errors...
  } else {
    // Mark the transaction as broadcasted
  }
});
```
