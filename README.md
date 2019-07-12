# GRT ERC20 token specification

GRT token is ERC20 smart-contract for Ethereum blockchain

<p>Symbol      : GRT</p>
<p>Name        : GoRecru.it ERC20 token</p>
<p>Total supply: 2,450,000.000.0000</p>
<p>Decimals    : 4</p>

## The Idea 
GoRecruit token sale goes through contributors dashboard, funds are collecting on HD individual BTC and ETH addresses. That allows us working Bitcoin and Ethereum sent from any type of wallets, including crypto exchanges accounts, and that is why we have not implemented any crowd sale functions in our smart-contract.  

Because of security reasons all collected funds are transferred to cold storage wallets on daily basis, meantime ERC20 tokens are transferred to contributors.

## Smart-contract
GRT is solidity smart-contract based on typical ERC20 implementation:
[https://theethereum.wiki/w/index.php/ERC20_Token_Standard](https://theethereum.wiki/w/index.php/ERC20_Token_Standard)

## Basic interface extensions
### Pausable smart-contract
To avoid any inconvenience for contributors during crowd sale campaign, we have implemented pause function that blocks all token transfers except owners transactions. 
Pause doesn't affect contract owners operations. After 1st of May 2019, if contract is paused, it is resumed and cannot be paused anymore. That guarantees full control over initially distributed tokens.  

### Mass sending
Since initial transfers are performed from secured workstation once in a day, we collect all balances and withdrawal requests from our ICO campaign management software and then send tokens using mass sending function. 

### Token burning procedure
Since there's no convenient way to implement token burn procedure when you accept multiple currencies, we haven't implemented any special token burn procedure, however all undistributed funds will be returned to 0x00000000000000000000000000000000000 address when crowd sale is finished.   


## Tests
We have implemented and performed tests in Python 3.64.    
We used Embark 3.10 for local testing and Rinkeby chain for deployed contract tests.
