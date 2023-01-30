# Minting UI for Wasm smart contract on Astar/Shiden

### This site is based on the great work of Hashlips. To build it from scratch please go to [Hashlips YouTube channel](https://www.youtube.com/channel/UC1LV4_VQGBJHTJjEWUmy8nA).
The site is adapted to communicate with Wasm contract on Shiden Network.

# HashLips NFT minting dapp 🔥


This repo provides a nice and easy way for linking an existing NFT smart contract to this minting dapp. There are two ways of using this repo, you can go the simple route or the more complex one.

The simple route is so simple, all you need to do is download the build folder on the release page and change the configuration to fit your needs. (Follow the video for a walk through).

The more complex route allows you to add additional functionality if you are comfortable with coding in react.js. (Follow the below instructions for a walk through).

## Installation 🛠️

Clone this project:

```sh
https://github.com/Maar-io/ink-mint-dapp
```

Make sure you have node.js and yarn installed and then run:

```sh
yarn install
```

Rut it on local with:
```sh
yarn start
```
## Usage ℹ️

In order to make use of this dapp, all you need to do is change the configurations to point to your smart contract as well as update the images and theme file.

For the most part all the changes will be in the `public` folder.


Note: this dapp is designed to work with this [PSP34 NFT smart contract](https://github.com/swanky-dapps/nft), that takes no parameters in the `mintNext()` function. But you can change that in the App.js file if you need to use functions like `mint()` which that takes 2 params.

## Configuration :factory:
To link up your existing smart contract, go to the `public/config/config.json` file and update the following fields to fit your smart contract, network and marketplace details. The cost field should be in wei.
Ignore (but keepp in config) all the rest of config parameters

```json
{
  "CONTRACT_ADDRESS": "b8QeEr72aJQKfaXcEDGwB5iwqGuF1b9oysHtj3nwMsdmgHa",
  "SCAN_LINK": "https://shiden.subscan.io/account/b8QeEr72aJQKfaXcEDGwB5iwqGuF1b9oysHtj3nwMsdmgHa",
  "NETWORK": {
    "NAME": "Shiden",
    "SYMBOL": "SDN",
    "ID": 336
  },
  "NFT_NAME": "ShidenGraffiti",
  "SYMBOL": "SHG",
  "MAX_SUPPLY": 100,
  "WEI_COST": "10000000000000000",
  "DISPLAY_COST": 1,
  "MARKETPLACE": "SubWallet",
  "MARKETPLACE_LINK": "https://",
  "WS_PROVIDER": "wss://rpc.shiden.astar.network"
}
```
#### Update Metadata
Make sure you copy the contract metadata from and paste it in the `src/redux/blockchain/abi.json` file.

#### Update Images
Now you will need to create and change 2 images and a gif in the `public/config/images` folder, 
* `bg.png`
* `example.gif`
* `logo.png`.

#### Update Theme
Next change the theme colors to your liking in the `public/config/theme.css` file.

```css
:root {
  --primary: #ebc908;
  --primary-text: #1a1a1a;
  --secondary: #ff1dec;
  --secondary-text: #ffffff;
  --accent: #ffffff;
  --accent-text: #000000;
}
```

#### Favicon
Now you will need to create and change the `public/favicon.ico`, `public/logo192.png`, and
`public/logo512.png` to your brand images.

Remember to update the title and description the `public/index.html` file

```html
<title>Nerdy Coder Clones</title>
<meta name="description" content="Mint your Nerdy Coder Clone NFT" />
```

Also remember to update the short_name and name fields in the `public/manifest.json` file

```json
{
  "short_name": "NCC",
  "name": "Coder Clone NFT"
}
```

After all the changes you can run.

```sh
yarn start
```


That's it! you're done.
