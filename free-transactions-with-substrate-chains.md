Before I answer this, it's important to realize that all of these decisions are in the hands of the blockchain developer using Substrate. Substrate itself doesn't care if you make a chain which is vulnerable to spamming. (Not saying you don't know this, but for the sake of everyone reading this...)

So... if you want to create a chain, you will need some sort of mechanism to prevent people from spamming the network and not allowing authorized transactions. There are a variety of ways to do this; simply having fees per transaction is the simplest and most straightforward. But there are other ways:

As you mentioned, an identity layer. If you trust the identity layer, you could provide a
limit of n transactions per day per identity or something.

Really, any system where Sybil protection is assumed to be done by some external entity off-chain could allow feeless tx's on-chain. But remember you are trusting that external identity!

Ignoring identity services, "x transactions per user per day" wouldn't help against a determined adversary, as it simple for them to make new accounts.

A global limiter like you mention would prevent most system-wide problems (i.e. chain would continue to produce blocks) but would likely drown out actual user activity with spam.

You could use some sort on-chain process to identity people or vote that accounts can/cannot have feeless transactions. This could be done manually or via some sort of automated process (but the latter would probably be gamed after a while).

A bond which can be slashed, e.g., you bond 100 FOO tokens, and if you are found guilty of spamming the network, you lose the FOO tokens. You can always create a new account and start spamming again, of course, but it would cost you 100 FOO tokens each time.

You could require an NFT (or one of a limited number of fungible tokens) to produce transactions.

You could have some other way of limiting transactions, e.g. by including a proof of work per transaction. I believe this is similar to how Nano works nowadays, after they experienced spamming problems.

These are just a few examples of what's possible with Substrate, btw. There are lots of other possibilities.