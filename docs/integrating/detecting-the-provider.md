---
sidebar_position: 1
---

# Detecting the Provider

To detect if a user has already installed Nix MOVE Wallet, a web application should check for the existence of a `nixwallet` object. Nix MOVE's browser extension and mobile in-app browser will both inject a `nixwallet` object into the window of any web application the user visits, provided that site is using `https://`, on `localhost`, or is `127.0.0.1`.

If a `nixwallet` object exists, Aptos/SUI apps can interact with Aptos/SUI via the API found at `window.nixwallet`. This `nixwallet` object is also available at `window.nixwallet`  to support legacy integrations.

To detect if Nix MOVE Wallet is installed, an application should check for an additional `isNixWallet` flag.

```javascript
window.nixwallet?.isNixWallet: boolean
```
