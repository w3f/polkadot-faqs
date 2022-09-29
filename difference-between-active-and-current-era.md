Active era = actual "current era"
Current era = currently planned era that we know the validator set for
My understanding (I have always found this confusing) is that current_era = active_era until the election of validators, then there is one session where current_era = active_era + 1
Ahh better description here:

https://github.com/paritytech/substrate/blob/5527263978a763bafc78d60955c662c20f465d18/frame/staking/src/pallet/mod.rs#L307

The current era = This is the latest planned era, depending on how the Session pallet queues the validator set, it might be active or not.

The active era = The era being currently rewarded. Validator set of this era must be equal to [SessionInterface::validators].