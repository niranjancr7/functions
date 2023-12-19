# Token

## Introduction

This repository contains a Solidity smart contract for an ERC-20 token named "Footbal" (with code "FB"). The contract is implemented using the OpenZeppelin library and includes additional functionality for burning tokens and transferring ownership.

## Smart Contract Details

### Token Features

1. **Name**: Footbal (FB)
2. **Supply**: The initial token supply is set to 0, and additional tokens can be minted by the contract owner.

### Contract Inheritance

The `Token` contract inherits functionality from the following OpenZeppelin contracts:

- ERC20: Implements the ERC-20 token standard.
- Ownable: Provides basic authorization control functionalities and simplifies the implementation of user permissions.
- ERC20Burnable: Adds the ability to burn (destroy) tokens.

### Constructor

The contract constructor initializes the token with the specified title, code, and assigns the initial supply to the contract deployer (initial owner).

### Functions

1. **mint**: Allows the contract owner to mint and distribute additional tokens to a specified trustee address.

    ```solidity
    function mint(address trustee, uint256 amountToMint) external onlyOwner;
    ```

2. **burn_**: Enables any token holder to burn a specified amount of their own tokens.

    ```solidity
    function burn_(uint256 amountToBurn) external;
    ```

3. **transfer_**: Allows the contract owner to transfer tokens from the contract to a specified trustee address.

    ```solidity
    function transfer_(address trustee, uint256 amountToTransfer) external onlyOwner returns (bool);
    ```

4. **getTitle**: Returns the title of the token.

    ```solidity
    function getTitle() external view returns (string memory);
    ```

5. **getCode**: Returns the code of the token.

    ```solidity
    function getCode() external view returns (string memory);
    ```

6. **getInitialSupply**: Returns the initial token supply.

    ```solidity
    function getInitialSupply() external view returns (uint256);
    ```

## Usage

1. Deploy the `Token` contract, providing the initial owner's address.
2. Interact with the contract using the provided functions to mint, burn, transfer tokens, and retrieve information about the token.

## Author

Niranjan D N

dnniranjan97@gmail.com

## License

This smart contract is licensed under the MIT License. See the [LICENSE](./LICENSE) file for details.
