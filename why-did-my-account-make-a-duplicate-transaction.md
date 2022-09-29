
Two submissions of the same extrinsic were made to the blockchain, about six hours apart. I'm not sure of _why_ this occurred (and I'm not familiar with Safepal), but I can explain _what_ happened.

First, note that unlike most blockchains, a transaction hash is not a globally unique identifier in Polkadot (see the wiki: https://wiki.polkadot.network/docs/build-protocol-info#unique-identifiers-for-extrinsics ) The _extrinsic ID_ is (once a block is finalized, of course). So the fact that the tx hash is the same means that the exact same transaction was submitted multiple times. Looking at the history of that account, it looks to be about six hours apart.

Also note that this transaction was submitted as immortal ( https://polkadot.subscan.io/extrinsic/0xccbbea4214ec68462b0581ca2c106118b2c2e6043f4cb3c75ea7e77bb15d810a ) - something that is specifically warned against, as it can allow replay attacks ( https://wiki.polkadot.network/docs/build-protocol-info#transaction-mortality ) . This is generally something in the control of the wallet, not the user.

During the first tx, the account was reaped (i.e. all DOT was sent out from it) . You can see the event here: https://polkadot.subscan.io/extrinsic/0xccbbea4214ec68462b0581ca2c106118b2c2e6043f4cb3c75ea7e77bb15d810a?event=10906629-18

Then a day later, the account was resurrected by sending in a little under 25 DOT - https://polkadot.subscan.io/extrinsic/0xfaed7db64a649d7979bf2d59d785495b6a95f6c31afae797ca4136b43b6248f0

For some reason, the original immortal transaction was then re-submitted. Now the account existed again, and this was a valid immortal transaction, so it got executed again.