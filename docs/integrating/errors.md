---
sidebar_position: 1
---

# Errors

When making requests to Nix Aptos Wallet in Establishing a Connection, Sending a Transaction, or Signing a Message, Nix Aptos Wallet may respond with an error. The following is a list of all possible error codes and their meanings.

| Code   |      Title      |  Description |
|:----------:|:-------------|:------|
| `10010000` |  `AN_ERROR_OCCURRED` | An error occurred |
| `10010001` |  `LOGIN_REJECT` | User rejected login request |
| `10010002` |  `SIGN_REJECT` | User rejected sign transaction request |
| `10010003` |  `PERSONAL_SIGN_REJECT`| User rejected the personal sign request |
| `10010004` |  `DISCONNECT_REJECT` | User rejected disconnect |
| `10010005` |  `CONNECT_REJECT`| User rejected connect |
| `10010006` |  `GET_NETWORKS_FAILED` | Failed to get networks |
| `10010007` |  `GET_NETWORK_FAILED` | Failed to get network |
| `10010008` |  `GET_ACCOUNTS_FAILED` | Failed to get accounts |
| `10010009` |  `GET_ACCOUNT_FAILED`| Failed to get account |
| `100100010` |  `CONNECT_FAILED` | Failed to connect wallet |
| `100100011` |  `DISCONNECT_FAILED` | Failed to disconnect wallet |
| `100100012` | `SIGN_FAILED`| Failed to sign transaction |
| `100100013` |  `PERSONAL_SIGN_FAILED` | Failed to sign message |

Typically, these errors will be easily parsable and have both a code and an explanation. For example:

```javascript
try {
  await window.nixwallet.getAccount();
} catch (err) {
//    {code: 10010001, message: 'User rejected login request'}
}
```