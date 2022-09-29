I saw the ECDSA signatures described as not BTC compatible. They are with a trivial conversion to include the flag byte, right?
flag referring to the 02/03 used for even/odd in compressed public keys, or... 27/28 used in ETH IIRC? Yet my main question is solely that there's nothing unexpected there (such as a different challenge algorithm)

I saw the ECDSA signatures described as not BTC compatible. They are with a trivial conversion to include the flag byte, right?
flag referring to the 02/03 used for even/odd in compressed public keys, or... 27/28 used in ETH IIRC? Yet my main question is solely that there's nothing unexpected there (such as a different challenge algorithm)
Afaik the flag should be either 0/1 or 27/28. Additionally, the issue is (was?) this -> https://docs.rs/libsecp256k1/0.7.0/libsecp256k1/struct.Signature.html#method.parse_overflowing
the Host, for example, exposes two version of ext_crypto_secp256k1_ecdsa_recover, where version one handles those non-standard, overflowing ECDSA signatures and version 2 only handles standard signatures. This is unrelated to the presumed BTC incompatibility, but I guess polkadot-js also used non-standard signatures
but I"m not sure

It is marked "incompatible" in polkadot-js since if you take the same mnemonic, it won't create the same private/public keys like in BTC. (Substrate uses mnemonic -> entropy as part of the derivation step). This is unlike the ed25519 Ledger type that follows the BTC/ETH/everything-else derivation path.