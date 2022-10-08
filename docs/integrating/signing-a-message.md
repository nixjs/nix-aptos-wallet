---
sidebar_position: 1
---

# Signing a Message

A web app can also request the user to sign a message, by using Nix Aptos Wallet API:

```javascript
await window.nixwallet.sign(msgData: string | Uint8Array, prefixMsg = 'Aptos Signed Message'): Promise<{signature: HexString}>
```

