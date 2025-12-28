// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import "@openzeppelin/contracts/token/ERC721/ERC721.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

contract SimpleNFT is ERC721, Ownable {
    uint256 public tokenIdCounter;

    constructor() ERC721("SimpleNFT", "SNFT") {}

    function mint(address to) public onlyOwner {
        tokenIdCounter += 1;
        _safeMint(to, tokenIdCounter);
    }
}
