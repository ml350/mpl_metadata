# Mint SPL Token

- Mint SPL Token with Metaplex Standards for Metadata. This example shows how to generate keypairs, deposit faucet solana and mint your token

## Setup Machine

1.) Install Homebrew: 

/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

2.) Install Solana CLI 

brew install solana

solana -- version (check if installed)

3.) Install node

brew install node

4.) Install SPL Token CLI

npm install -g @solana/spl-token-cli

spl-token --version

5.) Install Yarn

npm install --global yarn

yarn --version ( make sure to close and open terminal )

6.) Install esrun globally

npm i -g esrun

## Setup project

1.) Create new folder and copy mpl_metadata.ts

2.) Init yarn 

yarn init

3.) Add required dependecies

yarn add @solana/web3.js
yarn add @metaplex-foundation/mpl-token-metadata
yarn add @metaplex-foundation/umi
yarn add @metaplex-foundation/umi-bundle-defaults
yarn add @metaplex-foundation/umi-web3js-adapters

### Setup Accounts and Keypairs

solana-keygen grind --starts-with XYZ:1

(Response at the end should be "Wrote keypair to XYZRandomString.json")

solana config set -ud -k .\XYZRandomString.json

solana airdrop 2

solana-keygen grind --starts-with TokenSymbol:1

spl-token create-token

(The response would be address mint)

### Update code and Mint token and supply 

- On line 20 change .json to your XYZRandomString.json
- On line 21 change .json to your address_mint
- On line 24 you are changing this when you want to change network, devnet or mainnet-beta
- On line 28 ourMetadata, we input metadata for our token and uri as link of json file
- Run script with ``` esrun ./mpl_metadata.ts ```

spl-token create-account address_mint
spl-token mint address_mint 1000