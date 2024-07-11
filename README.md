# ZK circuit implementation
A hardhat circom project to make a circuit and verify it with a specified input values.

## Quick Start
Clone repo using `git clone https://github.com/mukul785/ZK-circuit-implementation.git`

### Install
`npm i`

### Compile
`npx hardhat circom` <br>
This will generate the **out** file with circuit intermediaries and generate the **CustomCircuitVerifier.sol** contract.

### Set-up
Create a .env file in root directory and enter private key of wallet that will be used to test circuit on amoy testnet with MATIC test tokens.<br>
Then paste this after 'solidity' in `hardhat.config.ts` <br>
`
networks: {
    amoy: {
      url: `https://rpc.ankr.com/polygon_amoy`,
      accounts: [process.env.AMOY_PRIVATE_KEY],
    },
  },
`
<br>
### Prove and Deploy
Run `npx hardhat run scripts/deploy.ts --network amoy` to compile, deploy, verify the test signals in the circuit.<br>
It should generate a contract address followed by 'true'.

### Verify on AMOY
Copy deployed contract address and search it on amoy testnet PolyScan, it will show the transaction of creation of contract verifying deploment of contract.
