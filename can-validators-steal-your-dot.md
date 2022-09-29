I would recommend reading the Staking section of the Polkadot Wiki to understand how it works.

Validators cannot "steal" your bonded DOT. However, if you are actively nominating a validator who commits an offense, you - and they - will be slashed. This would mean that a percentage of your bonded DOT would be locked and eventually sent to the Treasury (there is a delay for the Council to overrule this, if for instance the slashing was due to a software bug).

This is one of the reasons that you need to look closely at which validators you are nominating. We have an entire guide for this on the Polkadot Wiki here: https://wiki.polkadot.network/docs/learn-nominator#what-to-take-into-consideration-when-nominating Of special note is the self-stake of the validator. Slashes are the same percentage regardless of stake. Thus, a validator who is nominating itself with 10'000 DOT and faces a 0.5% slash, would lose 50 DOT themselves, along with 0.5% of whatever you are nominating them with.

Note that slashes are relatively rare, and almost all slashes are a very small percentage of bonded stake, unless many validators are taking part in the offense.