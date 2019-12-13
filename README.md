# Storing CLA Signatures on Ethereum Blockchain 
 
**On GitHub Actions Side**
1. Contributor signs CLA by copy & pasting the text into a comment 
2. GitHub Action checks whether the contributor's signature is already stored in the file which is specified in the CLA Workflow (= the local signature storage within the repository)
3. If the contributor's signature is not present in the local signature storage the GitHub Action will store the signature
4. If "Store To Blockchain" is active, GitHub Action calls a Post API which takes the values and stores them onto the Ethereum Blockchain 

**On Blockchain Access Side**
1. Post request is received and checked for consistency (call to GitHub API validating the data)
2. If everything is fine store the signature on the Ethereum Blockchain



# Rewards for Solved Issues 
## Coder Coin - ERC20
Smart Contract Adress: 0xb2259368b1691d49191C18571DE837911cB8597a
Link: https://etherscan.io/token/0xb2259368b1691d49191C18571DE837911cB8597a


Prerequisite for Receiving Code Coins: Brave Browser
If you do not have an Ethereum wallet yet, open the Brave Browser visit brave://wallet/ create a local wallet

## Scenario
1. The owner of a repository creates an issue and gives it a price tag - e.g. 100 Coder Coins (CC42) - storing it in a rewards folder
2. Contributor raises interest to solve an issue by writing a specific comment **I want to solve this issue**
3. GitHub Action checks for "I want to solve this issue" and creates a comment saying **Thank you very much. Please fork this repository and raise the PR when ready.**
4. Contributor raises PR
5. Owner should be notified
6. Owner Merges PR 
7. GitHub Action triggers transfer of reward amount in CCN from Owner to Contributor



# Background Info & Tutorials

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
5. compile
6. before clicking "deploy" select "Injected Web3" as Environment



### Unique Assets - Non-fungible token - ERC721

Ideas: data storage for one order



### Notes
curl -i https://api.github.com/users/michael-spengler/repos

