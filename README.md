### web3-notes

ideals:
- single observable lazy state tree

- emit top-level events for block, fork

- subscribe to logs, account balance/nonce/storage, etc

account.balance -> value is pumped to somewhere in state trie

- set focus via blocks-from-head parameter

always query state 5-blocks back from head, tx not 'firm' until 5 blocks back from head

- pipelines > callbacks

- submit tx, get results
```js
var pendingTx = exampleContract.foo.sendTransaction(2, {from: web3.eth.coinbase});
// transaction hash
pendingTx.getHash(funtion(err, result){ console.log(result) }) // tx hash
pendingTx.on('returnValue', function(err, returnValue){ console.log(returnValue) }) // tx return value
```
