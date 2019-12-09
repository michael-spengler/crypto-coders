# Steps To Create our Coin

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
