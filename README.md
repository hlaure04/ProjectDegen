# Project: Degen Token (ERC-20): Unlocking the Future of Gaming
## Description
Your task is to create a ERC20 token and deploy it on the Avalanche network for Degen Gaming. The smart contract should have the following functionality:
1. Minting new tokens: The platform should be able to create new tokens and distribute them to players as rewards. Only the owner can mint tokens.
2. Transferring tokens: Players should be able to transfer their tokens to others.
3. Redeeming tokens: Players should be able to redeem their tokens for items in the in-game store.
4. Checking token balance: Players should be able to check their token balance at any time.
5. Burning tokens: Anyone should be able to burn tokens, that they own, that are no longer needed.

# Getting Started
# Executing Program
- To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.
- Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar.
- Save the file with a .sol extension
- Copy and paste the following code into the file
- To compile the code, select the "Solidity Compiler" tab in the left-hand sidebar, change the "Compiler" option to "0.8.20"
- Then click the "Compile ProjectDegen.sol" button.
- To deploy the contract, choose the "ProjectDegen" contract from the dropdown menu and click the "Deploy" button.
- Interact with the contract by calling the require, revert, and assert function.

## Code Preview

function mint(address to, uint256 amount) external onlyOwner {
        require(to != address(0), "Invalid recipient address");
        require(amount > 300, "Amount must exceed 300");

        _mint(to, amount);
    }

     function redeemTokens(string memory itemName) external {
        require(bytes(itemName).length < 30, "Item name must be shorter than 30 characters");
        string memory lowercaseItemName = _toLower(itemName);
        require(SearchItem[lowercaseItemName] > 0, "Item must be on the list!");

        uint256 itemValue = SearchItem[lowercaseItemName];
        require(balanceOf(msg.sender) >= itemValue, "Not enough balance");

        _burn(msg.sender, itemValue);
    }

    function burn(uint256 amount) exte

  # Authors
Heleana V. Laure
8213709@ntc.edu.ph
