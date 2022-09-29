At a really high level, when a parachain first connects to the relay chain, it submits its genesis block and its runtime (defining the state transition function). At this point, the validators on the chain (via the Wasm and genesis stored on the chain itself) can, given a set of transactions, verify if it is valid or not, by running them against the Wasm and the known state. Collators on the parachain send collations of transactions to a randomly selected subset of validators, who verify that the state transition is valid (since they know both the previous state and the state transition function (STF), defined in the Wasm blob containing the runtime).

Other validators can verify that this is correct and slash an offending validator who tries to cheat by saying an invalid state transition is valid, since all of them have access to the current state as well as the STF. A block on a parachain is not considered finalized until its equivalent state transition has been validated on the relay chain. Thus, a parachain depends on the security of the relay chain.

Of course this elides a LOT of detail and wrinkles in operation. If you want to dig in deeper, I really recommend reading the Wiki page on the topic, or if you want to really dive in, reading the chapter on AnV (availability and validity) in the Polkadot Specification, put together by our great Spec Team.

How does XCM work?

XCM allows different chains to have a common way of interacting with each other using an "Esperanto" (common language) instead of every chain having to know exactly how other chains operate.

This is obviously a very high-level description! For more detail, I recommend reading Gav's description in the Medium post here: https://medium.com/polkadot-network/xcm-the-cross-consensus-message-format-3b77b1373392 or if you really want to dig in, you can review the code here: https://github.com/paritytech/polkadot/tree/59aa955576e963942c60e3ae8f8316444b66cafb/xcm

Collators?

Collators produce a collation (essentially, a candidate collection of transactions) on the parachain, which are sent to a randomly chosen subset of validators on the relay chain. The validators then verify that the collators provided a valid collation. It is a lot of work (ask anyone running a validator if they are seeing higher loads as the number of parachains increase). See https://spec.polkadot.network/#sect-collations

Smart contract logic is _part of_ the state transition; calls to smart contracts change the state of the chain. Any necessary smart contract logic is part of the runtime, which is known to the validators. The validators can then run the "candidate block" against this Wasm blob to ensure that it is valid. See https://spec.polkadot.network/#sect-parachain-runtime