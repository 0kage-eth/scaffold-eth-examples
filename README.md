# 🏗 Scaffold-ETH - 🎟 Harberger Tax NFT

> A test of a Harberger Tax NFT!

# What is it?

        Harberger Tax is a taxation method, which is highly effecient for public goods funding. It allows an ecosystem to strike a balance between pure private ownership, and total commons ownership of a resource or asset. It's quite simple, when someone claims an asset (in our case an NFT), they have to attach a price to it, that they pay a tax on (10%). And at any point in time anyone can buy that item for that declared price. This system makes it costly for users to unfairly price their assets, and mutually benefits the community if they were to.

        This contract is a sample contract that sends 50% of the taxes collected to be redistrubted within holders of the token, and the other 50% sent to my address.

# 🏃‍♀️ Quick Start
Required: [Node](https://nodejs.org/dist/latest-v12.x/) plus [Yarn](https://classic.yarnpkg.com/en/docs/install/#mac-stable) and [Git](https://git-scm.com/downloads)

```
git clone https://github.com/austintgriffith/scaffold-eth.git tax-nft
```
```
cd tax-nft 
git checkout tax-nft
yarn install
yarn start
```

> in a second terminal window, start your 📱 frontend:

```
cd tax-nft 
yarn chain
```

> in a third terminal window, 🛰 deploy your contract:

```
cd tax-nft 
yarn deploy --network NETWORK_OF_CHOICE (localhost, kovan, rinkeby, mainnet)
```

📱 Open http://localhost:3000 to see the app

👛 Open an incognito window and navigate to http://localhost:3000 (You'll notice it has a new wallet address).

⛽️ Grab some gas for each account using the faucet:

![nft4](https://user-images.githubusercontent.com/526558/124387005-55b34200-dcb3-11eb-8565-1ee40b5634ad.png)

🎟 Send an NFT to the incognito window address:

![nft5](https://user-images.githubusercontent.com/526558/124387008-58ae3280-dcb3-11eb-920d-07b6118f1ab2.png)

🕵🏻‍♂️ Inspect the `Debug Contracts` tab to figure out what address is the `owner` of `YourCollectible`?

💼 Edit your deployment script `deploy.js` in `packages/hardhat/scripts`

🔏 Edit your smart contract `YourCollectible.sol` in `packages/hardhat/contracts`

📝 Edit your frontend `App.jsx` in `packages/react-app/src`

🔑 Create wallet links to your app with `yarn wallet` and `yarn fundedwallet`

⬇️ Installing a new package to your frontend? You need to `cd packages/react-app` and then `yarn add PACKAGE`

# 📡 Deploy NFT smart contract!

🛰 Ready to deploy to a testnet?
> Change the `defaultNetwork` in `packages/hardhat/hardhat.config.js`

![nft6](https://user-images.githubusercontent.com/526558/124387061-7a0f1e80-dcb3-11eb-9f4c-19229f43adec.png)

🔐 Generate a deploy account with `yarn generate`

![nft7](https://user-images.githubusercontent.com/526558/124387064-7d0a0f00-dcb3-11eb-9d0c-195f93547fb9.png)

👛 View your deployer address using `yarn account` (You'll need to fund this account. Hint: use an instant wallet to fund your account via QR code)

![nft8](https://user-images.githubusercontent.com/526558/124387068-8004ff80-dcb3-11eb-9d0f-43fba2b3b791.png)

👨‍🎤 Deploy your NFT smart contract:

Make sure your target network is present in the hardhat networks config, then either update the default network in `hardhat.config.js` to your network of choice or run:

```
yarn deploy --network NETWORK_OF_CHOICE
```
> ✏️ Edit your frontend `App.jsx` in `packages/react-app/src` to change the `targetNetwork` to wherever you deployed your contract:

![nft9](https://user-images.githubusercontent.com/526558/124387095-9743ed00-dcb3-11eb-8ea5-afc25d7fef80.png)

You should see the correct network in the frontend:

![nft10](https://user-images.githubusercontent.com/526558/124387099-9a3edd80-dcb3-11eb-9a57-54a7d370589a.png)

🎫 Ready to mint a batch of NFTs for reals?
```
yarn mint
```
Once verified, they will then be available to view on Tenderly!

![nft11](https://user-images.githubusercontent.com/526558/124387132-b04c9e00-dcb3-11eb-95d1-03b8c272e52f.png)

# ⚔️ Side Quests
## 🐟 Open Sea
> Add your contract to OpenSea ( create -> submit NFTs -> "or add an existing contract" )

(It can take a while before they show up, but here is an example:)
https://testnets.opensea.io/assets/0xc2839329166d3d004aaedb94dde4173651babccf/1
## 🔍 Etherscan Contract Verification
> run yarn flatten > flat.txt (You will need to clean up extra junk at the top and bottom of flat.txt. Sorry, rookie stuff here.)

> copy the contents of flat.txt to the block explorer and select compiler v0.6.7 and Yes to Optimization (200 runs if anyone asks)

![nft12](https://user-images.githubusercontent.com/526558/124387153-c8bcb880-dcb3-11eb-8191-e53f87129b88.png)

## 🔶 Infura
> You will need to get a key from infura.io and paste it into constants.js in packages/react-app/src:

![nft13](https://user-images.githubusercontent.com/526558/124387174-d83c0180-dcb3-11eb-989e-d58ba15d26db.png)

# 🛳 Ship the app!
> ⚙️ build and upload your frontend and share the url with your friends...

```
# build it:

yarn build

# upload it:

yarn surge

yarn s3

yarn ipfs
```
![nft14](https://user-images.githubusercontent.com/526558/124387203-fe61a180-dcb3-11eb-8d68-82a76a514e43.png)

👩‍❤️‍👨 Share your public url with a friend and ask them for their address to send them a collectible :)

![nft15](https://user-images.githubusercontent.com/526558/124387205-00c3fb80-dcb4-11eb-9e2f-29585e323037.gif)

------------

# 🔭 Learning Solidity

📕 Read the docs: https://docs.soliditylang.org

📚 Go through each topic from [solidity by example](https://solidity-by-example.org) editing `YourContract.sol` in **🏗 scaffold-eth**

- [Primitive Data Types](https://solidity-by-example.org/primitives/)
- [Mappings](https://solidity-by-example.org/mapping/)
- [Structs](https://solidity-by-example.org/structs/)
- [Modifiers](https://solidity-by-example.org/function-modifier/)
- [Events](https://solidity-by-example.org/events/)
- [Inheritance](https://solidity-by-example.org/inheritance/)
- [Payable](https://solidity-by-example.org/payable/)
- [Fallback](https://solidity-by-example.org/fallback/)

📧 Learn the [Solidity globals and units](https://solidity.readthedocs.io/en/v0.6.6/units-and-global-variables.html)

# 🛠 Buidl

Check out all the [active branches](https://github.com/austintgriffith/scaffold-eth/branches/active), [open issues](https://github.com/austintgriffith/scaffold-eth/issues), and join/fund the 🏰 [BuidlGuidl](https://BuidlGuidl.com)!


 - 🚤  [Follow the full Ethereum Speed Run](https://medium.com/@austin_48503/%EF%B8%8Fethereum-dev-speed-run-bd72bcba6a4c)


 - 🎟  [Create your first NFT](https://github.com/austintgriffith/scaffold-eth/tree/simple-nft-example)
 - 🥩  [Build a staking smart contract](https://github.com/austintgriffith/scaffold-eth/tree/challenge-1-decentralized-staking)
 - 🏵  [Deploy a token and vendor](https://github.com/austintgriffith/scaffold-eth/tree/challenge-2-token-vendor)
 - 🎫  [Extend the NFT example to make a "buyer mints" marketplace](https://github.com/austintgriffith/scaffold-eth/tree/buyer-mints-nft)
 - 🎲  [Learn about commit/reveal](https://github.com/austintgriffith/scaffold-eth/tree/commit-reveal-with-frontend)
 - ✍️  [Learn how ecrecover works](https://github.com/austintgriffith/scaffold-eth/tree/signature-recover)
 - 👩‍👩‍👧‍👧  [Build a multi-sig that uses off-chain signatures](https://github.com/austintgriffith/scaffold-eth/tree/meta-multi-sig)
 - ⏳  [Extend the multi-sig to stream ETH](https://github.com/austintgriffith/scaffold-eth/tree/streaming-meta-multi-sig)
 - ⚖️  [Learn how a simple DEX works](https://medium.com/@austin_48503/%EF%B8%8F-minimum-viable-exchange-d84f30bd0c90)
 - 🦍  [Ape into learning!](https://github.com/austintgriffith/scaffold-eth/tree/aave-ape)

# 💬 Support Chat

Join the telegram [support chat 💬](https://t.me/joinchat/KByvmRe5wkR-8F_zz6AjpA) to ask questions and find others building with 🏗 scaffold-eth!

---

🙏 Please check out our [Gitcoin grant](https://gitcoin.co/grants/2851/scaffold-eth) too!
