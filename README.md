# Coder Coin - ERC20

Prerequisite: Brave Browser
If you do not have an Ethereum wallet yet, open the Brave Browser visit brave://wallet/ create a local wallet

## Contributer raises PR solving an issue claiming the Reward
1. The owner creates an issue and gives it a price tag using the Coders Coin - e.g. 100 Coder Coins (CCN)
2. Contributor raises interest to solve an issue by writing a specific comment "I want it now"
3. GitHub Action checks for "I want it now" and assign - if no one is assigned assigns the commenting user
4. Contributor raises PR
5. Owner Merges PR 
6. GitHub Action triggers transfer of reward amount in CCN from Owner to Contributor




## Steps To Create our Coin

1. Visit: http://remix.ethereum.org/
2. Create a file - e.g. coder-coin.sol - and add the following code:

```
pragma solidity ^0.5.0;
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/v2.3.0/contracts/token/ERC20/ERC20.sol";
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/v2.3.0/contracts/token/ERC20/ERC20Detailed.sol";
contract CCToken2 is ERC20, ERC20Detailed {
    constructor () public   ERC20Detailed("Coder Coin 2", "CC2", 0){
        _mint(msg.sender,20000000000 * (10 ** uint256(decimals())));
    }
}
```

3. Install the compile plugin
4. Install the deploy plugin



# Unique Assets - Non-fungible token - ERC721

Ideas: data storage for one order



# Data Storage for CLA signatures - Akshay

Scenario 1: (one contributor signs the CLA for the first time - no duplicate)
**On GitHub Actions Side**
1. Contributor signs CLA by copy & pasting the text into comment 
2. GitHub Action checks whether the contributor's signature is already stored in the file which is specified in the CLA Workflow (=the local signature storage within the repository)
3. If the contributor's signature is not present in the local signature storage the GitHub Action will store the signature
4. If "Store To Blockchain" is active, GitHub Action calls post API which takes the values and stores them onto the Ethereum Blockchain from where it could never be deleted. 

**On Blockchain Access Side**
1. Post request is received and checked for consistency (call to GitHub API validating the data)
2. If everything is fine store it as ERC721 unique asset






**On GitHub Actions Side**
