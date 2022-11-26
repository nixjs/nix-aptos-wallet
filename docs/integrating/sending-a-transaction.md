---
sidebar_position: 1
---

# Send a Transaction

A web app can also request the user to send a transaction, by using Nix MOVE Wallet API:

```javascript
export type Uint64 = bigint | number;
export interface OptionalTransactionArgs {
  maxGasAmount?: Uint64;
  gasUnitPrice?: Uint64;
  expireTimestamp?: number;
}
export interface TransactionRequest {
  ABI: ABI;
  extraArgs?: OptionalTransactionArgs;
}
export interface ABI {
  // Fully qualified module name, `AccountAddress::ModuleName`
  module: string;
  // Fully qualified func names, e.g. 0x1::Coin::transfer
  function: string;
  // TypeTag strings
  typeArguments: any[];
  arguments: any[];
}

const toDecimal= (value: string, dec: number) => {
    const v = new BigNumber(value)
    if (v.isNaN()) {
        return '0'
    }
    return v.times(new BigNumber(10).pow(dec)).toFixed()
}

const txnRequest: TransactionRequest = {
  ABI: {
    module: "0x1::coin",
    function: "transfer",
    typeArguments: ["0x1::aptos_coin::AptosCoin"],
    arguments: [
      BCS.bcsToBytes(
        TxnBuilderTypes.AccountAddress.fromHex(
          "0x8e11ce8e16b3d9701f08df9171a790ebdbca0a78010245427052b012faecc8a7"
        )
      ),
      BCS.bcsSerializeUint64(
        Number(toDecimal(String(1), BaseDecimals))
      ),
    ],
  },
};

await (window as any).nixwallet.signTransaction(txnRequest);
```
