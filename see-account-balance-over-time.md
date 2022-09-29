## How can I see account balance over time?

Go to https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Frpc.polkadot.io#/js

Enter the blocks you want to check.

Enter the following JavaScript code and execute it. Note that the results may not be in chronological order, you can copy/paste and sort them in a text editor or the Unix sort command to do so.

```
blocks = [2105, 1205309, 1205349];

const user = '1WG3jyNqniQMRZGQUc7QD2kVLT8hkRPGMSqAb5XYQM1UDxN';

blocks.forEach(calc);

async function calc(blockNum){
  const blockHash = await api.rpc.chain.getBlockHash(blockNum);
  const { data: { free: prev } } = await api.query.system.account.at(blockHash, user);
  console.log('Block', blockNum, ': user had a balance of', prev.toHuman());
}
```