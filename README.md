# lasmeta-alpha-nft

## Overview

The `ERC721CM` contract is a highly customizable ERC721 contract that includes several advanced features for managing NFT minting processes. It inherits from the `ERC721ACQueryable` and `Ownable` contracts and integrates additional functionality such as multiple minting stages, wallet-level minting limits, whitelist management, and anti-botting measures.

## Features

- **Multiple Minting Stages**: Supports multiple stages of minting with automatic switching based on time.
- **Wallet-Level Minting Limits**: Allows setting global and stage-specific limits for the number of tokens that can be minted per wallet.
- **Whitelist Management**: Uses a Merkle tree for managing whitelisted addresses.
- **Crossmint Support**: Integrates with Crossmint to facilitate easy NFT purchases.
- **Anti-Botting Measures**: Includes mechanisms to prevent bot activity during minting events.

## Contract Details

### ERC721CM.sol

\`\`\`solidity
pragma solidity ^0.8.4;

import "@openzeppelin/contracts/access/Ownable.sol";
import "@openzeppelin/contracts/security/ReentrancyGuard.sol";
import "@openzeppelin/contracts/token/common/ERC2981.sol";
import "@openzeppelin/contracts/utils/cryptography/ECDSA.sol";
import "@openzeppelin/contracts/utils/cryptography/MerkleProof.sol";
import "@openzeppelin/contracts/utils/cryptography/SignatureChecker.sol";
import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";
import "contracts/creator-token-standards/ERC721ACQueryable.sol";
import "./IERC721M.sol";

/**
 * @title ERC721CM
 *
 * @dev ERC721ACQueryable and ERC721C subclass with MagicEden launchpad features including
 *  - multiple minting stages with time-based auto stage switch
 *  - global and stage wallet-level minting limit
 *  - whitelist using merkle tree
 *  - crossmint support
 *  - anti-botting
 */
contract ERC721CM is IERC721M, ERC721ACQueryable, Ownable, ReentrancyGuard {
    using ECDSA for bytes32;
    using SafeERC20 for IERC20;

    // Contract variables...

    // Contract functions...
}
\`\`\`

### Functions

- **mint**: Allows minting of new tokens based on the current stage and wallet limits.
- **setWhitelist**: Sets the Merkle tree root for the whitelist.
- **setBaseURI**: Sets the base URI for token metadata.
- **setCrossmintAddress**: Sets the Crossmint address for facilitating crossmint transactions.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.
