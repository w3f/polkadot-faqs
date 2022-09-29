You can recover a 24 word seed phrase on Polkadot-JS UI or extension, but not create one. That will always be 12 words.

If the user REALLY wants to create a 24-word seed phrase, they can use `subkey generate --words 24`

```
% subkey generate --words 24
Secret phrase:       consider saddle monitor boost ostrich agent salon slab either visual food nerve tag help potato embark victory three borrow vivid have sauce soup list
  Secret seed:       0x9410330c46a7310f19e319f9701d42feae9fd19a453196aec40e9257a4f46f67
  Public key (hex):  0x88e83f4869d6ac593ccbae7e64714c513ddae08cfed007ff9d5e6b5c20892059
  Account ID:        0x88e83f4869d6ac593ccbae7e64714c513ddae08cfed007ff9d5e6b5c20892059
  Public key (SS58): 5FADMuhPk5puytZutHsztX6mfkiW2DGHUcsjumtniqoYCJca
  SS58 Address:      5FADMuhPk5puytZutHsztX6mfkiW2DGHUcsjumtniqoYCJca
```