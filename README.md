# Introduction

This repository holds a list of whitelisted tokens in the MultiversX web tools. A whitelisted token can have website and socials URLs, a logo or a description, that will be displayed on MultiversX products, such as the MultiversX Explorer or the Web Wallet. The logos are also used in the xPortal App.

# Tokens branding

Amplify your token brand via the MultiversX Network web tools & the Mobile Wallet.

Add a logo, description & socials for your ESDT token.

Project owners can create a PR to this repo. Create a folder named exactly as your ESDT ID or NFT Collection ID, i.e. TOKEN-abcc123. Add 2 files for the logo: `logo.png` and `logo.svg`. Also add an `info.json` file containing all the relevant information.

Alternatively, a token owner can use our dApp that facilitates the token branding: https://assets.multiversx.com 

| :exclamation:  Be aware of the repository's [environments](#environments) and [ownership checks](#ownership-checks). |
|----------------------------------------------------------------------------------------------------------------------|

## info.json

Here’s a prefilled template for the .json file to get you started:

```JSON
{
    "website": "https://www.multiversxtoken.com",
    "description": "The EGLD token is the utility token of MultiversX Token",
    "ledgerSignature": "1234",
    "social": {
        "email": "egld-token@multiversx.com",
        "blog": "https://www.multiversxtoken.com/EGLD-token-blog",
        "twitter": "https://twitter.com/EGLD-token-twitter",
        "whitepaper": "https://www.multiversxtoken.com/EGLD-token-whitepaper.pdf",
        "coinmarketcap": "https://coinmarketcap.com/currencies/EGLD-token",
        "coingecko": "https://www.coingecko.com/en/coins/EGLD-token"
    },
    "lockedAccounts": {
        "egld1alice": "Team vesting",
        "egld1bob": "Locked private sale"
    },
    "extraTokens": [
        "LPTOKEN-1234",
        "STAKED-1234"
    ],
    "status": "active"
}
```

- `ledgerSignature` will be generated by MultiversX. It will give your token “whitelist” status on the Ledger app and enable a more data rich flow for users storing your token on their Ledger hardware wallets. If one wants to set a Ledger signature, request it when opening a PR.
- `lockedAccounts` defines accounts that do not actively transfer tokens, which will be subtracted from the supply to determine the circulating supply of the token
- `extraTokens` defines tokens / MetaESDT collection identifiers that are part of the token itself (LP tokens, Farm tokens, Metastaking tokens, etc). These extra tokens will be also taken into consideration when calculating distinct `accounts` & total number of `transactions` in the token details API endpoint

## Guidelines:
- logo does not resemble MultiversX/Mobile Wallet logos, or other trademarked visual identities
- PR files need to be named info.json, logo.svg and logo.png
- the PR title has to be the token name + identifier (ex: TOKEN-abc123)
- max pic size 100kb (.png)

## Logos general requirements

- must look good also when cropped as a circle
- must define a transparent background
- must have sufficiently good contrast both when rendered on a light background, as well as a dark background

## logo.png

- mandatory when opening a pull request
- must have a resolution of 500x500 pixels

| ![RIDE png](https://github.com/multiversx/mx-assets/blob/master/tokens/RIDE-7d18e9/logo.png?raw=true) |
| :---------------------------------------------------------------------------------------------------: |
|                                               *Example*                                               |

## logo.svg

- mandatory when opening a pull request
- must have a square format

| ![RIDE svg](https://github.com/multiversx/mx-assets/blob/master/tokens/RIDE-7d18e9/logo.svg?raw=true) |
| :---------------------------------------------------------------------------------------------------: |
|                                               *Example*                                               |

# Identities branding

Amplify your staking brand via the MultiversX Network web tools & the Mobile Wallet.

Add a logo, description & socials for your staking identity.

Project owners can create a PR to this repo. Create a folder named as your identity (lowercase, dash-separated. Example: my-staking-identity). Add a logo.png file, sized 500x500. Also add an info.json file containing all the relevant information.

| :exclamation:  Be aware of the repository's [environments](#environments) and [ownership checks](#ownership-checks). |
|----------------------------------------------------------------------------------------------------------------------|

## info.json

```JSON
{
  "description": "Description of the Staking provider.",
  "name": "My Staking Provider",
  "website": "https://www.mywebsite.com/",
  "twitter": "MyStakingProvider",
  "owners": [
    "erd1qyu5wthldzr8wx5c9ucg8kjagg0jfs53s8nr3zpz3hypefsdd8ssycr6th",
    "erd1qqqqqqqqqqqqqqqpqqqqqqqqqqqqqqqqqqqqqqqqqqqqpq8llllskj52rl"
  ]
}
```

Inside the `owners` array, depending on your needs, you should include:
- if you'd like to brand directly staked nodes (no staking provider), then add the owner address
- if you'd like to brand a staking provider, then add the staking provider's address
- both if you'd like to brand directly staked nodes and a staking provider under the same identity

## logo.png

- must be 200x200
- must look good also when cropped as a circle
- must define a transparent background
- must have sufficiently good contrast both when rendered on a light background, as well as a dark background

# Accounts branding

Amplify your project via the MultiversX Network web tools & the Mobile Wallet.

Add a description, an icon & socials for your Smart Contract or address.

Addresses owners can create a PR to this repo. Create a file named as your address with a `json` extenstion (Example: `erd1qyu5wthldzr8wx5c9ucg8kjagg0jfs53s8nr3zpz3hypefsdd8ssycr6th.json`). 

| :exclamation:  Be aware of the repository's [environments](#environments) and [ownership checks](#ownership-checks). |
|----------------------------------------------------------------------------------------------------------------------|

## address.json

Example: 

`erd1qyu5wthldzr8wx5c9ucg8kjagg0jfs53s8nr3zpz3hypefsdd8ssycr6th.json`

```JSON
{
  "name": "My branded address or SC",
  "description": "",
  "social": {
    "website": "https://dapp.com",
    "twitter": "https://twitter.com/intent/user?screen_name=dapp",
    "telegram": "https://t.me/Dapp",
    "youtube": "https://youtube.com/@Dapp",
    "github": "https://github.com/Dapp"
  },
  "tags": [
    "dapp",
    "smartcontract"
  ],
  "icon": "mydapp"
}
```

## icon

If you also want to include an icon that will be displayed near your address, you must add a PNG and a SVG icon in the nearby `icons` directory that will be named exactly as the `icon` field value inside the json file + the `png` and `svg` extensions. 

Example: If one wants to brand a devnet account, then an `<address>.json` file needs to be added inside `devnet/accounts` directory. For example, if the `icon` value is `myaddress` then `myaddress.png` + `myaddress.svg` files must be added inside `devnet/accounts/icons` directory.

The same logo guidelines used for tokens/identities apply here as well. 

# Environments

This repository enable users to brand their asset on any of our environments (Mainnet, Testnet, and Devnet).

Therefore, here are the directories that one needs to use depending on the environment: 
- for a mainnet asset, refer to the `tokens`, `accounts` or `identities` directory.
- for a testnet asset, refer to the `testnet/tokens`, `testnet/accounts` or `testnet/identities` directory.
- for a devnet asset, refer to the `devnet/tokens`, `devnet/accounts` or `devnet/identities` directory.

# Ownership checks

To make sure that assets can only be branded by real owners, we introduced a GitHub action that requires that an ownership check is successful before allowing the PR to be merged.

This is done via a message signature verification, where the message is the latest commit sha of the PR (to avoid multiple signs in case of intermediary merges, if one of the signature is verified, it is enough).

To do so, on the PR page, go to the `Commits` tab of the Pull Request and copy the latest commit hash (should look similar to `9c6164f1b195ce96bc5b65d6878ebe813e852550`). Then sign 
that string by using the owner of the asset you are branding. The easiest way is to use our [Utils Dapp](https://utils.multiversx.com) where you should log in with the owner wallet
and then go to he 'Sign Message' tab and sign the commit hash previously copied. After that, leave a comment inside the Pull Request with the obtained signature.
