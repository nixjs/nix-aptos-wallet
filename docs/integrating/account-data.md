---
sidebar_position: 1
---

# Account Data

## getAccount

```javascript
await window.nixwallet.getAccount(): Promise<{
        index: number
        name: string
        address: string
        derivationPath: string
        publicKey?: string
        display: boolean
    }>
```

## getAccounts

```javascript
await window.nixwallet.getAccounts(): Promise<{
        index: number
        name: string
        address: string
        derivationPath: string
        publicKey?: string
        display: boolean
    }[]>
```

## getNetwork

```javascript
await window.nixwallet.getNetwork(): Promise<{
        chainID: string
        name: string
        nodeURL: string
        faucetURL: string
        explorerURL: string
        nativeToken: string
        type: 'testnet' | 'mainnet' | 'Devnet'
    }>
```

## getNetworks

```javascript
await window.nixwallet.getNetworks(): Promise<{
        chainID: string
        name: string
        nodeURL: string
        faucetURL: string
        explorerURL: string
        nativeToken: string
        type: 'testnet' | 'mainnet' | 'Devnet'
    }[]>
```
