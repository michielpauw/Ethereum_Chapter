# Preparation Session 3

- Follow the steps from this tutorial to install the MetaMask browser Extension, and to create a wallet: https://www.geeksforgeeks.org/how-to-install-and-use-metamask-on-google-chrome/ (if you use a different browser, you can download the extension here: https://metamask.io/download/). You can do this on your ING computer, as well as on your private computer, if you prefer.
- You can now see an account (for example, 0xbC28c434aa54Cb0b3F1eA70cf02073DeB0E400DE, with most likely 0 ETH in it). Copy this account, and send it to me on Teams. I will make sure that you get some Test Ether (no real value, so sorry to disappoint)
- With the extension open, you can see `Ethereum Mainnet` in the top of the Extension popup. Click on this, and in the dropdown menu that appears click on `Show/hide test networks` and toggle this control to On.
- Now, in the same dropdown menu, click on `Ropsten Test Network`. This is the Ethereum test network that we will be using. After I have sent you some Test Ether, this should be visible in this window.
- You are now all set for the third session on Blockchain!

# Session 3

## Let's deploy some smart contracts!

We will use Remix IDE to write, compile, and deploy Smart Contracts for Ethereum. We will start with a very small example that is included with the IDE itself.

- Go to https://remix.ethereum.org
- In the File Explorer, check out the `contracts` folder, and then the file `2_Owner.sol`
- As you can see, we have a `contract` called `Owner`

  - The contract sets the private field `owner` to the deployer of the contract
  - The current `owner` can set the variable to a different user
  - The `owner` can be retrieved

- You can compile the 2_Owner.sol contract by right clicking on the file and clicking `compile`
- Make sure there is no error message in the second tab on the left
- In the third tab, you can deploy the contract
  - Choose `Environment: Injected Web 3`. A popup may come from MetaMask to confirm
  - Make sure that the `Account` is set to an account that has some (test) ether available (make sure that your MetaMask is set to the Ropsten test network)
  - The `Gas Limit` and `Value` can be ignored for now
  - Make sure that the `Contract` is set to `Owner - contracts/2_Owner.sol`
  - Click `Deploy`, but do not click `Confirm` yet in the MetaMask popup
  - We will dive a bit deeper into what everything means, but for now, in the MetaMask popup:
    - Click on `Site Suggested`, you are redirected within the popup to 'Edit gas fee'
    - Click on 'Market' or 'Aggresive' (the latter will cost more test Ether)
    - Click on `Confirm`
  - The deployment of the contract starts. This will take some time, so this is a good time to continue reading a bit!

## Your first transaction

You just started the deployment of your first Smart Contract. Congratulations! In the console at the bottom of the Remix IDE, you can click on `view on etherscan`. Click this to see the status of the transaction. Most likely, most of the details are 'Pending', and there is not a lot of information that you get from this page. If you click on MetaMask, you also see the Contract Deployment, with a Pending status. From experience, the deployment can take between one and ten minutes, but the speed and price of a transaction depend on a number of things.

Before we investigate this, it is good to know the basic Ether conversions that you will encounter: 1 ether = 10^9 gwei = 10^18 wei. To put that into a 'time perspective': on the Ropsten test network, it took me 30 hours to mine approximately 9 ether, and then in the following 15 hours I did not mine a single block. 9 ether should be enough for all of us for the remainder of this workshop, though.

### What are gas price, gas limit, and all those values?

As you know from previous sessions, every transaction requires computational effort, and therefore every transaction requires a fee.

- The fundamental unit of computation in Ethereum is called 'gas'. A standard Ether transaction requires 21.000 units of gas, a Smart Contract deployment may require much more.
- For every unit of gas that is used in a transaction, a fee is paid, most often denoted in gwei
- The gas fee per unit, is calculated as the `base fee + priority fee`
- In order for a transaction to be eligible for inclusion in a block, at least the base fee must be paid. This fee is determined by how 'busy' the Blockchain network currently is, and it often is only a fraction of the total fee.
- The priority fee (or tip) can be set by the user initiating the transaction, to incentivize miners to include the transaction in a block. Withouth this fee, it can take very long for a transaction to complete. This fee (often) makes up the main chunk of a transaction fee.
- The Gas Limit denotes the max units of gas used for a transaction (a security mechanism to prevent high fees from a bug or error in a Smart Contract, for example). The difference between gas units used, and gas limit, are not charged.
- Total cost of a transaction, therefore, becomes `gas units (max. gas limit) \* (base fee + tip)

### My transaction is slow, now what?

- Click on the MetaMask extension and find your pending transaction
- Click on 'Speed up'
- You will be asked if you want to increase the gas price, i.e., increase the Priority Fee for the transaction
- If you confirm, a new transaction will be started (the hash will change), and this transaction will (most likely) finish faster than the previous transaction.
