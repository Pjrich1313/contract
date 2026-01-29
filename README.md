# CATX Token Contract

This repository contains the CATX token smart contract for Binance Smart Chain.

## 🚀 Automated Compilation

This repository includes a GitHub Actions workflow that automatically compiles the CATX.sol contract whenever code is pushed to the main/master branch.

### What the Workflow Does

The automated workflow (`.github/workflows/deploy.yml`) performs the following steps:

1. **Compiles the Contract**: Uses solc compiler to compile CATX.sol with optimization
2. **Generates Artifacts**: Creates bytecode and ABI files
3. **Uploads Artifacts**: Stores compilation artifacts for download
4. **Provides Deployment Instructions**: Displays comprehensive deployment guidance

### Accessing Compiled Artifacts

After each workflow run:

1. Go to the **Actions** tab in this repository
2. Click on the latest workflow run
3. Scroll down to **Artifacts**
4. Download `catx-contract-complete` artifact
5. Extract the zip file to get:
   - `CATX_bytecode.bin` - Contract bytecode
   - `CATX_abi.json` - Contract ABI
   - `CATX_contract.json` - Combined contract artifact
   - `deploy-sample.js` - Sample deployment script
   - `DEPLOYMENT_INSTRUCTIONS.md` - Detailed deployment guide

## ⚠️ Security Warning

**IMPORTANT**: 

- **NEVER** commit private keys to this repository
- **NEVER** store private keys in GitHub Actions or any CI/CD system
- **ALWAYS** deploy contracts manually from a secure local environment
- **ALWAYS** use environment variables for sensitive data

The workflow compiles the contract but does NOT deploy it. Deployment must be done manually for security reasons.

## 📋 Deployment Instructions

For detailed deployment instructions to BSC Testnet or Mainnet, please refer to the `DEPLOYMENT_INSTRUCTIONS.md` file included in the workflow artifacts.

### Quick Start for BSC Testnet

1. Download the artifacts from the latest workflow run
2. Install dependencies: `npm install ethers`
3. Get testnet BNB from: https://testnet.binance.org/faucet-smart
4. Set your private key: `export PRIVATE_KEY="your-key"`
5. Run the deployment script: `node deploy-sample.js`

### BSC Testnet Configuration

- **RPC URL**: https://data-seed-prebsc-1-s1.binance.org:8545/
- **Chain ID**: 97
- **Currency**: tBNB
- **Explorer**: https://testnet.bscscan.com

## 📄 Contract Details

- **Token Name**: CATX
- **Symbol**: CATX
- **Total Supply**: 1,000,000,000,000
- **Solidity Version**: ^0.6.12

### Tokenomics

- 30% Liquidity Pool
- 10% Save Cats
- 10% Burn
- 20% Community
- 10% Early Backers
- 10% Validators
- 10% Foundation

### Transaction Fees

- **Buy**: No fees
- **Sell**: 
  - 2% automatically burned
  - 3% automatically added to LP
  - 2% distributed to holders
  - 3% sent to marketing wallet

## 🔧 Manual Compilation

If you need to compile manually:

```bash
solc --optimize --optimize-runs 200 --bin --abi --output-dir ./build CATX.sol
```

## 📚 Resources

- [BSC Documentation](https://docs.binance.org/smart-chain/)
- [PancakeSwap](https://pancakeswap.finance/)
- [BscScan](https://bscscan.com/)
- [Ethers.js Documentation](https://docs.ethers.io/)

## 🤝 Contributing

This is a token contract repository. Please ensure all changes are thoroughly tested before proposing modifications.

## 📞 Support

For questions or issues related to deployment, please refer to the DEPLOYMENT_INSTRUCTIONS.md file in the artifacts.

---

**Website**: www.catxtoken.com
