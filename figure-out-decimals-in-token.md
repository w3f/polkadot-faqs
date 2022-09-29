You can verify this by doing an RPC call for system.properties and look at tokenDecimals key.

https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fwestend-rpc.polkadot.io#/rpc

Westend:

```
system.properties: ChainProperties
{
  ss58Format: 42
  tokenDecimals: [
    12
  ]
  tokenSymbol: [
    WND
  ]
}
```

Polkadot:

```
 system.properties: ChainProperties
{
  ss58Format: 0
  tokenDecimals: [
    10
  ]
  tokenSymbol: [
    DOT
  ]
}
```