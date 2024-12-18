## Frontend Developer Test Prompt

### Overview

You are tasked with creating a Next.js application that integrates web3 functions to display token information and user balance using TailwindCSS for styling. This test is designed to assess your skills in frontend development, particularly in using Next.js, TailwindCSS, and integrating with blockchain technologies using specific libraries.

# Token to use
- Token: ynETHx
- Chain: Holesky
- Address: 0xfd930060e51C10CCBc36F512676B4FD3E7026a1E
- Abi: Check the github repo in file `ynETHx.abi.tsx`. You can import the abi to where you need it.
- deposit function name: deposit
- withdraw function name: redeem (This allows you to redeem your tokens for wETH)
- You do no have to use ynETHx. You may also use any other token you want on any chain you wish that satisfy the requiremnts of this test.

### Requirements

#### Setup a Next.js Application

1. **Initialize a new Next.js project.**
   - Setup a new Next.js app with app router, and tailwindCSS. All the default suggestions when creating a new next app can be used.
2. **Install Necessary Libraries**
   - Add the following libraries to the project:
     - [`viem@2.x`](https://viem.sh/)
     - [`wagmi` (version 2)](https://wagmi.sh/)
     - [`@tanstack/react-query`](https://tanstack.com/query/latest)
     - [`@rainbow-me/rainbowkit`](https://www.rainbowkit.com/docs/introduction)
   - Use libraries for blockchain interactions.
3. **Web3Modal WalletConnect Integration**
   - Implement Rainbow Kit to connect to web3 wallets such as MetaMask. custom connect button.
   - The connect wallet button should be placed in a navbar.
   - The connection button in the header should display "Connect" when the user is not connected to a wallet. Once connected, it should show the user's truncated Ethereum address (e.g., "0x12...ab34").
   - Make sure you are connected to Holesky if using ynETHx or the network your token is on if using a different token.
4. **Create a Web3 Hook**
   - Develop a hook to manage and provide Web3 data throughout the app. This hook should provide the user's web3 address, the connected chain ID, and a boolean called isActive indicating if the wallet is connected.
   - Example usage: `const { address, chainID, isActive } = useWeb3()`
   - Name the hook useWeb3, and which can be imported anywhere in the app to access the above data.
5. **Develop a Reusable Hook for Token Information**
   - Create a custom hook (`useTokenData`) that fetches and returns information about any ERC20 token. The hook should return the following data structure:
     ```json
     {
       "tokenAddress": '',
       "tokenName": '',
       "symbol": '',
       "tokenSupply": 0n,
       "userBalance": 0n,
       "tokenDecimals": ''
     }
     ```
   - This hook will be used to display token information on the main page.
6. **Design the Main Page**
   - Nav bar with any brand logo you want on the left, and a web3 connect button on the right.
   - On the main page, display three cards. Each card should show a piece of information fetched by your `useTokenData` hook (e.g., Token Symbol, Token Name, Token Decimals).
   - Ensure the cards are displayed in a row on medium breakpoints (md) and above, and stacked vertically on smaller screen sizes.
   - Below the cards, display the user's balance and the token supply in ether (human-readable) values.
8. **Deposit Form**

- Create a deposit and withdraw function that allows the user to deposit tokens into the contract, and updates the users balance dynamically.
- Feel free to use any past number converting logic you have implemented in the past to speed up setting up the deposit function.
- This should be a simple form with a single input field for the amount of tokens to deposit, and a submit button.

### Additional Guidelines

- You are free to use any code snippets provided from the web3modal walletconnect docs, wagmi, or viem libraries. Do not copy code from other sources expect what has been mentioned in the deposit form.
- Focus on creating a clean, user-friendly UI and ensure the application is responsive across different devices.
- Pay attention to code organization and best practices in React and Next.js development.

### Submission

- Bonus: Depoloy your app using Vercel. (it is free for a hobby project)
- Include a link to your GitHub repository containing the project code.
- We will review your code in the interview, and do a small live coding test building on this take home test.

This test is designed to evaluate your ability to create a modern web application using Next.js, integrate with web3 libraries, and apply best practices in frontend development. Good luck!

# Example Final Product

![Desktop view example](/example-1.png)
![Mobile view example](/example-2.png)
