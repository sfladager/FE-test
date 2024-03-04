## Frontend Developer Test Prompt

### Overview

# You are tasked with creating a Next.js application that integrates with Ethereum blockchain to display token information and user balance using TailwindCSS for styling. This test is designed to assess your skills in frontend development, particularly in using Next.js, TailwindCSS, and integrating with blockchain technologies using specific libraries.

### Requirements

# Setup a Next.js Application

## Frontend Developer Test Prompt

### Overview

You are tasked with creating a Next.js application that integrates web3 functions to display token information and user balance using TailwindCSS for styling. This test is designed to assess your skills in frontend development, particularly in using Next.js, TailwindCSS, and integrating with blockchain technologies using specific libraries.

# Token to use

- Token: ynETH
- Chain: Goerli
- Address: 0x0091626e15caFd0F6Bc96dE7F12CEe444c0a212d
- Abi: Check the github repo. You can import the abi with the following import cmd: 'import YNETH_ABI from '@/lib/abi/ynETH.abi'
- deposit function name: depositETH
  ( you may also use any other token you want on any chain you wish that you can satisfy the requiremnts of this test with.)

### Requirements

#### Setup a Next.js Application

1. **Initialize a new Next.js project.**
   - Configure TailwindCSS for styling. Refer to the TailwindCSS documentation for setup instructions.
2. **Install Necessary Libraries**
   - Ensure the following libraries are installed in your project:
     - `viem`
     - `wagmi` (version 2)
     - `@web3modal/wagmi`
   - These libraries will be used for blockchain interactions and UI components.
3. **Web3Modal WalletConnect Integration**
   - Implement Web3Modal to connect to Ethereum wallets. Use the `@web3modal/wagmi` library for integration.
   - The connection button in the header should display "Connect" when the user is not connected to a wallet. Once connected, it should show the user's truncated Ethereum address (e.g., "0x12...ab34").
4. **Create a Web3 Context**
   - Develop a context to manage and provide Web3 data throughout the application. This context should provide the user's Ethereum address, the connected chain ID, and a boolean indicating if the wallet is connected.
   - Example usage: `const { address, chainID, isActive } = useWeb3()`
5. **Develop a Reusable Hook for Token Information**
   - Create a custom hook (`useTokenData`) that fetches and returns information about an ERC20 token. The hook should return the following data structure:
     ```json
     {
       "tokenAddress": "string",
       "tokenName": "string",
       "symbol": "string",
       "tokenSupply": "bigint",
       "userBalance": "bigint",
       "tokenDecimals": "string"
     }
     ```
   - This hook will be used to display token information on the main page.
6. **Design the Main Page**
   - On the main page, display three cards. Each card should show a piece of information fetched by your `useTokenData` hook (e.g., Token Symbol, Token Name, Token Decimals).
   - Ensure the cards are displayed in a row on medium breakpoints (md) and above, and stacked vertically on smaller screen sizes.
   - Below the cards, display the user's balance and the token supply in ether (human-readable) values.
7. **Deposit Form**

- Create a deposit function that allows the user to deposit tokens into the contract, and updates the users balnce dynamically.
- Feel free to use any past number converting logic you have implemented in the past to speed up setting up the deposit function.

### Additional Guidelines

- You are free to use any code snippets provided from the web3modal walletconnect docs, wagmi, or viem libraries. Do not copy code from other sources unless mentioned elsewhere.
- Focus on creating a clean, user-friendly UI and ensure the application is responsive across different devices.
- Pay attention to code organization and best practices in React and Next.js development.

### Submission

- Your application should be deployed and accessible online. Provide the URL to your deployed application.
- Include a link to your GitHub repository containing the project code.

This test is designed to evaluate your ability to create a modern web application using Next.js, integrate with Ethereum blockchain, and apply best practices in frontend development. Good luck!

# Example Final Product

![Description of the image](/path/to/your/image.jpg)
