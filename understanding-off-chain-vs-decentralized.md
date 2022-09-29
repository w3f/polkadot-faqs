PFS is decentralized, even though it's not using blockchain ( https://ipfs.tech/ ) - it's not at all the same as putting something on a Google Cloud server. Same with Crust.

Conversely, on-chain does not necessarily mean decentralized ( see this article from a former W3F Tech Ed team member - https://bitfalls.com/hr/2020/05/25/opinion-on-private-blockchains/ ).

It's important to realize that technically, a blockchain is just a linked list with hash pointers. There's nothing about the blockchain data structure itself that promotes decentralization, just immutability. You can _use_ this data structure with other technology to _make_ something decentralized and there are a lot of benefits to doing so.

Plenty of things can happen "off-chain" while still being decentralized. The chain can even prove that computations are happening correctly or are not being manipulated (see zero-knowledge proofs, various L2s, Substrate's off-chain workers, etc.)

Regarding your question, I disagree completely. Yes, there are projects which are nothing more than money grabs, and there are chains which pay only lip service to decentralization. But personally, I see massive potential in having code and data which is provably immutable and transparent. I wouldn't be in this space otherwise.

If you are interested in digging into all of this further, my lectures on blockchain fundamentals are (in my biased opinion, of course!) a good place to start - https://mooc.web3.foundation/

Not to mention, you CAN use remarks to store data entirely on-chain if you want ( just like you could e.g. use OP_RETURN on Bitcoin). I'm just saying that if this causes scalability issues ( a common problem due to the blockchain model itself ), then there are other ways to do it and still remain decentralized.