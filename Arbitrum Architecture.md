# Arbitrum Architecture

## Overview

For ToG, Arbitrum was chosen as the standard DeFi layer to manage token rewards, game fees, NFTs, staking-to-play, and other functionalities.
This is because it's the most popular Ethereum L2 and has the most liquidity bar Ethereum L1 (or other alt-L1s). It was also chosen as it's an EVM, 
which is beneficial when further expanding to other chains using Paima. Overall, going EVM maximizes player reachability.

Key functions in Arbitrum will include the following:
1. Buying unique player NFTs
2. Staking tokens to play the game
3. Depositing entry fees to play in tournaments with prize pools.
4. Communicating with Mina through zkBridge (Might be ethereum only atm, will be doing more research on this soon) 

## Player NFT
- Each player can purchase their own player nft. 
- Essentially represents their player stats and progress in ToG
- Includes stats like wins, losses, matches played, types of matches played (1 v 5/10/50/100)
- Projected NFTs using Paima's primitive stack

## Stake-To-Play
- In order to play ToG, players need to stake varying token amounts.
- Works similar to a subscription, a "stake-scription" if you will.
- The following stake options will be used to start (can and probably will change over time)
  - 0.01 ETH or 25 USDC: Base tier of the game. Unlimited free play. Not eligible for tournament play. 
  - 0.1 ETH or 250 USDC: Mid tier of the game. Unlimited free play. Limited to 10 tournament games per day.
  - 1 ETH or 2500 USDC: High tier of the game. Unlimited free paly. Limited to 50 tournament games per day. 