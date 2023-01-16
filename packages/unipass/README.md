# @web3-onboard/unipass

## UniPass is a non-custodial smart contract wallet that provides a seedless and gasless user experience

### Install

`npm i @web3-onboard/core @web3-onboard/unipass`

## Options

```typescript
type UniPassProviderOptions = {
  chainId: number;
  returnEmail: boolean;
  appSettings?: {
    appName?: string;
    appIcon?: string;
    theme?: UniPassTheme;
  };
}
```

## Usage

```typescript
import Onboard from '@web3-onboard/core'
import unipassModule from '@web3-onboard/unipass'

// initialize the module with options
const unipass = unipassModule({
  chainId: 80001,
  returnEmail: true,
  appSettings: {
    appName: "web3-onboard test for unipass",
    theme: UniPassTheme.DARK,
  },
});


const onboard = Onboard({
  // ... other Onboard options
  wallets: [
    unipass
    //... other wallets
  ]
})

const connectedWallets = await onboard.connectWallet()
console.log(connectedWallets)
```
