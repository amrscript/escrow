# Escrow Smart Contract

This repository contains a Solidity smart contract for a basic Escrow system. The contract facilitates a secure transaction between a buyer and a seller, with an escrow agent holding the funds until certain conditions are met.

## Features

- **Role-Based Access**: Only the buyer, seller, or escrow agent can perform specific actions.
- **State Management**: Tracks the status of the escrow (Created, Funded, Completed, Cancelled).
- **Event Logging**: Emits events for key actions to allow for easy monitoring and integration with front-end applications.

## Smart Contract Overview

### Contract Name: `Escrow`

- **Constructor**: Initializes the contract with the buyer (deployer), seller's address, and the escrow agent's address.
- **States**:
  - `Created`: Initial state after deployment.
  - `Funded`: State after the buyer funds the escrow.
  - `Completed`: State after the escrow agent completes the transaction.
  - `Cancelled`: State if the escrow is cancelled.

### Functions

1. **`fund()`**: 
   - Allows the buyer to fund the escrow by sending Ether.
   - Only callable by the buyer when in the `Created` state.

2. **`complete()`**: 
   - Allows the escrow agent to complete the transaction, transferring the funds to the seller.
   - Only callable by the escrow agent when in the `Funded` state.

3. **`cancel()`**: 
   - Allows the escrow agent to cancel the escrow and refund the buyer.
   - Only callable by the escrow agent when in the `Funded` state.

### Example Usage

1. **Compile the Contract**:
   - Use a Solidity compiler (e.g., Remix IDE or Hardhat) to compile the `Escrow` contract.

2. **Deploy the Contract**:
   - Deploy the contract by providing the seller's address and the escrow agent's address. The deployer will be the buyer.

3. **Fund the Escrow**:
   - The buyer calls the `fund()` function and sends Ether to fund the escrow.

4. **Complete the Transaction**:
   - The escrow agent calls the `complete()` function to transfer the funds to the seller.

5. **Cancel the Escrow**:
   - The escrow agent can call the `cancel()` function to refund the buyer if the transaction does not go through.

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/escrow-smart-contract.git
   cd escrow-smart-contract
