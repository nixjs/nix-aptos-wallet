---
sidebar_position: 1
---

# Establishing a Connection

Once an application has detected the provider, it can then request to connect to Aptos. This connection request will prompt the user for permission to share their public key, indicating that they are willing to interact further. Users must approve a connection request before the app can make additional requests such as signing a message or sending a transaction.
Once permission is established for the first time, the web application's domain will be whitelisted for future connection requests. After a connection is established, it is possible to terminate the connection from both the application and the user side.

## Connecting

The recommended and easiest way to connect to Aptos is by calling:

```javascript
await window.nixwallet.connect(): Promise<{
        index: number
        name: string
        address: string
        derivationPath: string
        publicKey?: string
        display: boolean
    }>
```

**NOTE**: After the user has approved the connection for the first time, the web app's domain will be remembered for the future sessions.

## Disconnecting

When you want the web app to forget about the connection status with Nix Aptos Wallet, you can do this by calling `nixwallet.disconnect()` in your web app. See below:

```javascript
await window.nixwallet.disconnect(): Promise<{
        name: string
        url: string
        image: string
    }>
```

**NOTE**: After disconnecting, the web app must reconnect to Nix Aptos Wallet to make requests.

## Changing Accounts

Coming soon

## Changing Networks

Coming soon
