# 🏗 Scaffold-ETH

> is everything you need to get started building decentralized applications powered by smart contracts using Chainlink oracles and vrf

🧪 Quickly experiment with Solidity using a frontend that adapts to your smart contract:

![image](https://user-images.githubusercontent.com/2653167/124158108-c14ca380-da56-11eb-967e-69cde37ca8eb.png)

```bash
git clone -b chainlink-tutorial-1 https://github.com/austintgriffith/scaffold-eth.git

# 🏄‍♂️ Quick Start

### Manual setup

Prerequisites: [Node](https://nodejs.org/en/download/) plus [Yarn](https://classic.yarnpkg.com/en/docs/install/) and [Git](https://git-scm.com/downloads)

> clone/fork 🏗 scaffold-eth:

```bash
git clone https://github.com/austintgriffith/scaffold-eth.git
```

> generate your account to deploy to testnet:

```bash
cd scaffold-eth
yarn generate
```

The warnings are normal and you can ignore.
![image](https://user-images.githubusercontent.com/9419140/106749563-ac2d2f00-65f4-11eb-91a5-d736e30f4b97.png)


``` bash
yarn account
```

You will need to fund your deployer account with kovan ETH before you can deploy your contracts.

Testnet ETH is available from https://faucet.kovan.network/

![image](https://user-images.githubusercontent.com/9419140/106749192-36c15e80-65f4-11eb-8365-64f66569c899.png)


```bash
yarn deploy

```

![image](https://user-images.githubusercontent.com/9419140/106748708-9b2fee00-65f3-11eb-90c6-3c28c09f7540.png)


🔏 Edit your smart contract `YourContract.sol` in `packages/hardhat/contracts`
🔏 Edit your smart contract `ApiConsumer.sol` in `packages/hardhat/contracts`
🔏 Edit your smart contract `CoinGeckoConsumer.sol` in `packages/hardhat/contracts`
🔏 Edit your smart contract `RandomNumberConsumer.sol` in `packages/hardhat/contracts`

📝 Edit your frontend `App.jsx` in `packages/react-app/src`

💼 Edit your deployment script `deploy.js` in `packages/hardhat/scripts`

📱 Open http://localhost:3000 to see the app

📚 Keep [solidity by example](https://solidity-by-example.org) handy and check out the [Solidity globals and units](https://docs.soliditylang.org/en/v0.8.10/units-and-global-variables.html)

> With everything up your UI should look something like this:

![image](https://user-images.githubusercontent.com/9419140/106748778-b0a51800-65f3-11eb-8a57-d6444748ffe9.png)

> Fund the contract with LINK 

> ** Side Quest - use deploy.js to fund the contract with LINK after funding deployer account. **

- Testnet LINK is available from https://kovan.chain.link/ 

Copy the contract address and send it some link. You don't need much, average oracle costs .1 LINK.
![image](https://user-images.githubusercontent.com/9419140/106750100-645ad780-65f5-11eb-95c9-ce07ef0ed2e2.png)

To test just put a arbitrary number in the field and click send.

![image](https://user-images.githubusercontent.com/9419140/106750387-c74c6e80-65f5-11eb-9c19-74ead780dc5b.png)

After about 30 seconds you can click the refresh icon to get the value.

![image](https://user-images.githubusercontent.com/9419140/106750667-1e524380-65f6-11eb-8983-d4fd6a392b1c.png)

> Now, what do we do with it?

Let's roll some dice... We used an event to record the roll from the VRF contract.

![image](https://user-images.githubusercontent.com/9419140/106751049-afc1b580-65f6-11eb-93c6-69fd9295d0db.png)


![image](https://user-images.githubusercontent.com/9419140/106750992-9ae52200-65f6-11eb-9a35-8a09a31b051c.png)

As you can see the event emitted our 6 dice roll values and we can now use them in the front-end.

> Here is the solidity code broken down

![image](https://user-images.githubusercontent.com/9419140/106750921-7db05380-65f6-11eb-9b25-1b377a997d43.png)


---

> There are two other Chainlink examples...

APIConsumer.sol

- This contract shows you how to use any API to make a get request.

![image](https://user-images.githubusercontent.com/9419140/106782214-e52acb00-6617-11eb-9213-b119e1eb94f3.png)

CoinGeckoConsumer.sol

- This contract shows you how to use existing Chainlink jobs.

![image](https://user-images.githubusercontent.com/9419140/106782323-04295d00-6618-11eb-9ff7-4de13698b23f.png)


> 🔁    You can `yarn deploy` any time and get a fresh new contract in the frontend:

Make sure to edit your deploy.js if you don't want to redeploy all of your contracts.

![deploy](https://user-images.githubusercontent.com/2653167/93149199-f8fa8280-f6b2-11ea-9da7-3b26413ec8ab.gif)


---

🔐 Global variables like `msg.sender` and `msg.value` are cryptographically backed and can be used to make rules

📝 Keep this [cheat sheet](https://solidity.readthedocs.io/en/v0.7.0/cheatsheet.html?highlight=global#global-variables) handy

⏳ Maybe we could use `block.timestamp` or `block.number` to track time in our contract

🔏 Or maybe keep track of an `address public owner;` then make a rule like `require( msg.sender == owner );` for an important function

🧾 Maybe create a smart contract that keeps track of a `mapping ( address => uint256 ) public balance;`

🏦 It could be like a decentralized bank that you `function deposit() public payable {}` and `withdraw()`

📟 Events are really handy for signaling to the frontend. [Read more about events here.](https://solidity-by-example.org/events)

📲 Spend some time in `App.jsx` in `packages/react-app/src` and learn about the 🛰 [Providers](https://github.com/austintgriffith/scaffold-eth#-web3-providers)

⚠️ Big numbers are stored as objects: `formatEther` and `parseEther` (ethers.js) will help with WEI->ETH and ETH->WEI.

🧳 The single page (searchable) [ethers.js docs](https://docs.ethers.io/v5/single-page/) are pretty great too.

🐜 The UI framework `Ant Design` has a [bunch of great components](https://ant.design/components/overview/).

📃 Check the console log for your app to see some extra output from hooks like `useContractReader` and `useEventListener`.

🏗 You'll notice the `<Contract />` component that displays the dynamic form as scaffolding for interacting with your contract.

🔲 Try making a `<Button/>` that calls `writeContracts.YourContract.setPurpose("👋 Hello World")` to explore how your UI might work...

💬 Wrap the call to `writeContracts` with a `tx()` helper that uses BlockNative's [Notify.js](https://www.blocknative.com/notify).

🧬 Next learn about [structs](https://solidity-by-example.org/structs/) in Solidity.

🗳 Maybe an make an array `YourStructName[] public proposals;` that could call be voted on with `function vote() public {}`

🔭 Your dev environment is perfect for *testing assumptions* and learning by prototyping.

📝 Next learn about the [fallback function](https://solidity-by-example.org/fallback/)

💸 Maybe add a `receive() external payable {}` so your contract will accept ETH?

🚁 OH! Programming decentralized money! 😎 So rad!

🛰 Ready to deploy to a testnet? Change the `defaultNetwork` in `packages/hardhat/hardhat.config.js`

🔐 Generate a deploy account with `yarn generate` and view it with `yarn account`

🔑 Create wallet links to your app with `yarn wallet` and `yarn fundedwallet`

⬇️ Installing a new package to your frontend? You need to `cd packages/react-app` and then `yarn add PACKAGE`

⬇️ Installing a new package to your backend? You need to `cd packages/harthat` and then `yarn add PACKAGE`

( You will probably want to take some of the 🔗 [hooks](#-hooks), 🎛 [components](#-components) with you from 🏗 scaffold-eth so we started 🖇 [eth-hooks](https://www.npmjs.com/package/eth-hooks) )

🚀 Good luck!


---------------------------------------------------

BELOW is the readme from the master branch
- SEE WHAT TO INCLUDE IN THE ABOVE (do we deploy locally in the tutorial?)
- See what to change / add in the above (mocks etc.)




----------------------------------------------------
FROM MASTER 



yarn install
yarn chain
```

> in a second terminal window, start your 📱 frontend:

```bash
cd scaffold-eth
yarn start
```

> in a third terminal window, 🛰 deploy your contract:

```bash
cd scaffold-eth
yarn deploy
```

🌍 You need an RPC key for production deployments/Apps, create an [Alchemy](https://www.alchemy.com/) account and replace the value of `ALCHEMY_KEY = xxx` in `packages/react-app/src/constants.js`

🔏 Edit your smart contract `YourContract.sol` in `packages/hardhat/contracts`

📝 Edit your frontend `App.jsx` in `packages/react-app/src`

💼 Edit your deployment scripts in `packages/hardhat/deploy`

📱 Open http://localhost:3000 to see the app

### Automated with Gitpod

To deploy this project to Gitpod, click this button:

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#github.com/scaffold-eth/scaffold-eth)

# 📚 Documentation

Documentation, tutorials, challenges, and many more resources, visit: [docs.scaffoldeth.io](https://docs.scaffoldeth.io)

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
