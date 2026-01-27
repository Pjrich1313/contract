# CATX Token - Community Fever 🐱

Welcome to the CATX Token contract repository! This README provides comprehensive information about the CATX token, its features, and step-by-step instructions for deployment.

## 📋 Table of Contents

- [Overview](#overview)
- [Token Parameters](#token-parameters)
- [Token Distribution](#token-distribution)
- [Fee Structure](#fee-structure)
- [Key Features](#key-features)
- [Smart Contract Details](#smart-contract-details)
- [Deployment Instructions](#deployment-instructions)
- [Contract Verification](#contract-verification)
- [Important Addresses](#important-addresses)

## 🌟 Overview

CATX is a community-driven token with automatic liquidity generation, token burns, holder rewards, and marketing allocation on every sell transaction. The token is built on the Binance Smart Chain (BSC) and follows the BEP-20 standard.

**Website:** [www.catxtoken.com](https://www.catxtoken.com)

## 🔧 Token Parameters

| Parameter | Value |
|-----------|-------|
| **Token Name** | CATX |
| **Symbol** | CATX |
| **Decimals** | 9 |
| **Total Supply** | 1,000,000,000,000 (1 Trillion) |
| **Blockchain** | Binance Smart Chain (BSC) |
| **Contract Standard** | BEP-20 |

## 📊 Token Distribution

The total supply of 1 trillion CATX tokens is distributed as follows:

| Allocation | Percentage | Amount |
|------------|-----------|--------|
| Liquidity Pool | 30% | 300,000,000,000 |
| Save Cats | 10% | 100,000,000,000 |
| Burn | 10% | 100,000,000,000 |
| Community | 20% | 200,000,000,000 |
| Early Backers | 10% | 100,000,000,000 |
| Validators | 10% | 100,000,000,000 |
| Foundation | 10% | 100,000,000,000 |

## 💰 Fee Structure

### Buy Transactions
✅ **NO FEES** on buy transactions

### Sell Transactions
On every sell transaction, a total of **10%** fee is applied and distributed as follows:

| Fee Type | Percentage | Description |
|----------|-----------|-------------|
| **Burn Fee** | 2% | Automatically burned, reducing total supply |
| **Liquidity Fee** | 3% | Automatically added to the liquidity pool |
| **Reflection Fee** | 2% | Automatically distributed to all token holders |
| **Marketing Fee** | 3% | Sent to the marketing wallet for project growth |

### Marketing Wallet Address
```
0x19B5585056fa6E13FCeD8cCB3CbBFBB63a07C59d
```

## ✨ Key Features

1. **Zero Buy Fees**: No fees on purchasing CATX tokens
2. **Automatic Liquidity**: 3% of every sell is added to the liquidity pool
3. **Deflationary Mechanism**: 2% of every sell is automatically burned
4. **Holder Rewards**: 2% of every sell is redistributed to all holders
5. **Marketing Support**: 3% of every sell funds marketing initiatives
6. **Anti-Whale Protection**: Maximum transaction and wallet size limits
7. **Ownership Controls**: Owner can manage fees, exclusions, and limits
8. **Reflection Mechanism**: Passive rewards for holding CATX

## 🔐 Smart Contract Details

The CATX token contract is built using Solidity 0.6.12 and includes:

- **SafeMath Library**: Protection against integer overflow/underflow
- **Ownable Pattern**: Secure ownership management
- **Reflection Mechanism**: Reward distribution to holders
- **Uniswap V2 Integration**: Automated liquidity on PancakeSwap
- **Fee Exclusion System**: Ability to exclude addresses from fees
- **Swap and Liquify**: Automatic conversion and liquidity addition

### Router Address (BSC Mainnet)
```
0x10ED43C718714eb63d5aA57B78B54704E256024E
```
This is the PancakeSwap V2 Router address on BSC.

## 🚀 Deployment Instructions

Follow these step-by-step instructions to compile and deploy the CATX token contract using Remix IDE:

### Step 1: Set Up Remix IDE

1. Open your web browser and navigate to [Remix IDE](https://remix.ethereum.org)
2. You'll see the Remix interface with a file explorer on the left

### Step 2: Create the Contract File

1. In the **File Explorer** panel (left sidebar), click the **"+"** icon to create a new file
2. Name the file `CATX.sol`
3. Copy the entire contents of the CATX.sol contract from this repository
4. Paste it into the newly created file in Remix

### Step 3: Compile the Contract

1. Click on the **"Solidity Compiler"** tab in the left sidebar (icon looks like "S")
2. Select compiler version **0.6.12** from the dropdown menu
3. Enable **"Auto compile"** (optional but recommended)
4. Click the **"Compile CATX.sol"** button
5. Wait for compilation to complete - you should see a green checkmark if successful
6. If there are any warnings, you can safely ignore them as long as there are no errors

### Step 4: Connect Your Wallet

1. Install [MetaMask](https://metamask.io) browser extension if you haven't already
2. Configure MetaMask for **Binance Smart Chain**:
   - Network Name: `BSC Mainnet`
   - RPC URL: `https://bsc-dataseed.binance.org/`
   - Chain ID: `56`
   - Symbol: `BNB`
   - Block Explorer: `https://bscscan.com`
3. Ensure you have enough BNB in your wallet for deployment gas fees (approximately 0.1-0.3 BNB)

### Step 5: Deploy the Contract

1. Click on the **"Deploy & Run Transactions"** tab (icon looks like Ethereum logo with arrow)
2. In the **ENVIRONMENT** dropdown, select **"Injected Provider - MetaMask"**
3. MetaMask will prompt you to connect - click **"Connect"**
4. Verify that your account address appears in the **ACCOUNT** field
5. In the **CONTRACT** dropdown, select **"CATX"**
6. Click the **"Deploy"** button (orange button)
7. MetaMask will pop up asking you to confirm the transaction
8. Review the gas fee and click **"Confirm"**
9. Wait for the transaction to be confirmed on the blockchain (usually 10-30 seconds)
10. Once deployed, you'll see your contract under **"Deployed Contracts"** at the bottom

### Step 6: Verify Deployment

1. Click the dropdown arrow next to your deployed contract
2. You should see all the contract functions listed
3. Click on **"totalSupply"** to verify it returns `1000000000000000000000` (1 trillion with 9 decimals)
4. Click on **"name"** to verify it returns `CATX`
5. Click on **"symbol"** to verify it returns `CATX`
6. Copy the contract address displayed at the top of the deployed contract section

### Step 7: Important Post-Deployment Steps

After deployment, the deployer address will receive all 1 trillion tokens. You should:

1. **Exclude Addresses from Fees**: Call `excludeFromFee()` for addresses that shouldn't pay fees
2. **Exclude from Rewards**: Call `excludeFromReward()` for addresses like liquidity pools
3. **Set Maximum Transaction Amount**: Call `setMaxTxPercent()` if needed (default is set)
4. **Add Liquidity**: Transfer tokens to PancakeSwap and create the liquidity pool
5. **Distribute Tokens**: Send tokens to the addresses according to the token distribution plan
6. **Renounce or Lock Ownership**: For community trust, consider renouncing ownership after setup

## 🔍 Contract Verification

To verify your contract on BSCScan:

### Option 1: Using BSCScan's Web Interface

1. Go to [BSCScan](https://bscscan.com)
2. Search for your deployed contract address
3. Click on the **"Contract"** tab
4. Click **"Verify and Publish"**
5. Fill in the following details:
   - **Compiler Type**: Solidity (Single file)
   - **Compiler Version**: v0.6.12+commit.27d51765
   - **License Type**: Unlicensed
6. Paste the entire contract source code from CATX.sol
7. Set **Optimization**: No
8. Click **"Verify and Publish"**
9. Wait for verification to complete

### Option 2: Using Remix IDE

1. In Remix, after deploying the contract, click on the **"Plugin Manager"** (plug icon in left sidebar)
2. Search for and activate **"Flattener"** plugin
3. Click on **"Flattener"** in the left sidebar
4. Click **"Flatten CATX.sol"**
5. Save the flattened contract code
6. Follow Option 1 steps using the flattened code

## 📍 Important Addresses

### Default Addresses in Contract

| Purpose | Address |
|---------|---------|
| Marketing Wallet | `0x19B5585056fa6E13FCeD8cCB3CbBFBB63a07C59d` |
| PancakeSwap V2 Router | `0x10ED43C718714eb63d5aA57B78B54704E256024E` |

**Note**: The marketing wallet address can be updated by the contract owner using the `setMarketingWallet()` function if needed.

## ⚙️ Owner Functions

The contract owner has access to several administrative functions:

- `setTaxFeePercent(uint256)` - Set reflection fee percentage
- `setLiquidityFeePercent(uint256)` - Set liquidity fee percentage
- `setMarketingFeePercent(uint256)` - Set marketing fee percentage
- `setBurnFeePercent(uint256)` - Set burn fee percentage
- `setMaxTxPercent(uint256)` - Set maximum transaction percentage
- `setMaxWalletPercent(uint256)` - Set maximum wallet percentage
- `setMarketingWallet(address)` - Change marketing wallet address
- `excludeFromReward(address)` - Exclude address from receiving reflections
- `includeInReward(address)` - Include address in reflections
- `excludeFromFee(address)` - Exclude address from paying fees
- `includeInFee(address)` - Include address in fee payments
- `setSwapAndLiquifyEnabled(bool)` - Enable/disable automatic liquidity

## 📝 License

This contract is unlicensed. Please review and ensure compliance with your local regulations before deployment.

## ⚠️ Disclaimer

This is a smart contract that will be deployed on the blockchain. Once deployed, it cannot be modified. Please ensure you:

- Thoroughly test the contract on testnet before mainnet deployment
- Understand all functions and their implications
- Have sufficient BNB for gas fees
- Keep your private keys secure
- Understand the risks associated with cryptocurrency and smart contracts

## 🔗 Additional Resources

- [Remix IDE](https://remix.ethereum.org)
- [BSCScan](https://bscscan.com)
- [PancakeSwap](https://pancakeswap.finance)
- [MetaMask](https://metamask.io)
- [Binance Smart Chain Documentation](https://docs.binance.org/smart-chain/developer/deploy/remix.html)

## 📧 Support

For questions or support, please visit [www.catxtoken.com](https://www.catxtoken.com)

---

**Made with ❤️ by the CATX Community**
