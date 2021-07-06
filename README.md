# Quickswap WBTC-USDC Liquidity Pool Yield Farming (Polygon Mainnet)

This mix is configured for use with [Ganache](https://github.com/trufflesuite/ganache-cli) on a [forked mainnet](https://eth-brownie.readthedocs.io/en/stable/network-management.html#using-a-forked-development-network).

<img src="https://user-images.githubusercontent.com/47485188/124619284-23ae0580-de96-11eb-9c64-088af0b219e6.png"> </img>

## How it Works
### Deposit
The Strategy takes Quickswap's Quick-v2 WBTC-USDC Liquidity Pool tokens as deposit and stakes them on Quickswap for yield generation. You can get Quick-v2 WBTC-USDC tokens [here](https://quickswap.exchange/#/add/0x1BFD67037B42Cf73acF2047067bd4F2C47D9BfD6/0x2791Bca1f2de4661ED88A30C99A7a9449Aa84174)
### Harvest & Compounding
Including the APY from providing liquidity in the WBTC-USDC pool, the user also gets QUICK rewards for staking the WBTC-USDC LP tokens.

The strategy converts the QUICK tokens to 50% WBTC & 50% USDC. Then it adds them to the WBTC-USDC Liquidity Pool on Quickswap for WBTC-USDC LP Tokens. 

These WBTC-USDC LP Tokens are then reinvested back into the strategy for further yield generation.
### Withdrawing Funds
On withdraw call, the strategy simply unstakes the WBTC-USDC tokens and returns them back to the user based on the number of vault shares that the user owns.

## [Expected Yield](https://quickswap.exchange/#/quick)

As of July 5, 2021

Rewards -> 9.71% APY <br>
Fees -> 10.77% APY

Total -> <strong>20.48% APY</strong>

## Notes
1. Add Polygon to your local brownie networks
```
brownie networks import network-config.yaml
```
2. Increase the default balance of an account (since we are dealing with Matic here)
```
brownie networks modify polygon-main-fork default_balance="1000000 ether"
```

## Tests
<img src="https://user-images.githubusercontent.com/47485188/124650917-e8bcc980-deb7-11eb-9344-c25a3c4d2f6d.png"> </img>