You are looking for calls to democracy.fast_track. It is a bit confusing, since most explorers have trouble finding extrinsics inside of batch calls, and batch calls are the normal way to fast-track proposals.

But what you CAN do is look for calls to technicalCommittee.close, which close and execute a decision by the Technical Committee. You can do that on Subscan here: https://polkadot.subscan.io/extrinsic?address=&module=technicalcommittee&call=close&result=all&signedChecked=all&startDate=&endDate=&startBlock=&timeType=date&version=9270&endBlock=

But now you want to see what those fast track's actually did. The easiest way is to click on the extrinsic and see what events occurred. For example, this was the most recent: https://polkadot.subscan.io/extrinsic/12116335-2

Looking at the events, you can see that after the close, an approval occurred, and Referendum 75 ( https://polkadot.subscan.io/referenda/75 ) started. Thus, Referendum 75 was first-tracked. Click on the link to Referendum 75 and you can see the parameters involved in the fast-track.