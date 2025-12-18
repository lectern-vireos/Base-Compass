# Base Compass (Built for Base)


Base Compass is a browser-first reference project that validates Base wallet connectivity, explicit chain targeting, and read-only onchain telemetry using Coinbase and Base tooling. It is designed for clarity, auditability, and compatibility with account abstraction–ready environments.

---

## Base ecosystem alignment

Built for Base.

Supported networks:
- Base Mainnet  
  chainId (decimal): 8453  
  Explorer: https://basescan.org  

- Base Sepolia  
  chainId (decimal): 84532  
  Explorer: https://sepolia.basescan.org  

The application explicitly targets Base networks and uses official Base RPC endpoints for all reads.

---

## What the script does

The app.base-compass.ts script provides an in-browser interface that:

1) Connects a wallet using Coinbase Wallet SDK  
2) Reads and validates the active chainId  
3) Performs read-only Base RPC queries:
   - latest block number  
   - ETH balance of the connected address  
4) Produces a “network pulse” snapshot:
   - block number and timestamp  
   - gas usage  
   - fee estimates  
5) Allows ETH balance checks for arbitrary addresses  
6) Prints Basescan links for verification  

No transactions are sent. All operations are read-only.

---

## Repository structure

- app.base-compass.ts  
  Browser-based script that connects to a wallet, toggles Base networks, and inspects onchain telemetry.

- contracts/  
  Solidity contracts deployed to Base Sepolia for testnet validation:
  - ERC721.sol — minimal contract used to track ownership of each token ID
  - contract.sol — simple stateful contract for interaction testing  

- package.json  
  Dependency manifest including Coinbase SDKs and 2–5 repositories from the Base GitHub organization.

- README.md  
  Technical documentation, Base references, licensing, and testnet deployment records.

---

## Libraries used

- @coinbase/wallet-sdk  
  Wallet connection layer compatible with Coinbase tooling and Base accounts.

- viem  
  RPC client used for Base reads, block inspection, and fee estimation.

- Coinbase GitHub repositories  
  Included as dependencies to reference the broader Coinbase open-source ecosystem.

- Base GitHub repositories  
  Included as dependencies to document linkage with Base tooling and infrastructure.

---

## Installation and execution

Install dependencies using Node.js.  
Serve the project with a modern frontend dev server and open the page in a browser.

Expected result:
- Connected address printed with Basescan link  
- Active chainId displayed (8453 or 84532)  
- Read-only Base RPC data displayed  
- Network pulse snapshot available on demand  

---

## License

MIT License

Copyright (c) 2025 YOUR_NAME

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

---

## Author

GitHub: https://github.com/lectern-vireos

Email: lectern_vireos_0h@icloud.com

Public contact: https://x.com/greeneemily4_4

---

## Testnet Deployment (Base Sepolia)

As part of pre-production validation, one or more contracts may be deployed to the Base Sepolia test network to confirm correct behavior and tooling compatibility.

Network: Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

Contract #1 address:  
0xc313c9ee6c3bFC4BC13a18993d932d639d9d0c74

Deployment and verification:
- https://sepolia.basescan.org/address/0xc313c9ee6c3bFC4BC13a18993d932d639d9d0c74
- https://sepolia.basescan.org/0xc313c9ee6c3bFC4BC13a18993d932d639d9d0c74/0#code  

Contract #2 address:  
0x5C545aE35bEF86ad1783e80dfB4d0C1bE8BEdE46

Deployment and verification:
- https://sepolia.basescan.org/address/0x5C545aE35bEF86ad1783e80dfB4d0C1bE8BEdE46
- https://sepolia.basescan.org/0x5C545aE35bEF86ad1783e80dfB4d0C1bE8BEdE46/0#code  

These testnet deployments provide a controlled environment for validating Base tooling, account abstraction flows, and read-only onchain interactions prior to Base Mainnet usage.
