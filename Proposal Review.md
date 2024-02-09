# PROPOSAL REVIEW

## I would like to understand a bit more about the requirement of using MINA in your project. Please further explain why MINA.

The main reason for choosing MINA over other platforms for Tower of Greed is to leverage MINA's recursive zk proof system to create scalable game instances. When playing ToG, players send actions, like moving and attacking, in parallel. Because of this, these actions are private inputs that cannot be sent as open and public transactions to a typical blockchain functioning as a public ledger. To solve this issue of having a game require secret inputs WHILE NOT relying on a trusted third party (which is how games are usually built in a server model), we use MINA's smart contract and zkprogram libraries to build the game. More specifically, this will be done by using Zeko L2 instances, which would be faster and provide more throughput for individual game instances while not depending on a centralized game server to act honest. Instead the game node will be responsible for proving the user's inputs and creating recursive proofs that contain the state of the game over time. 

ToG is heavily inspired by the proposed model written by Paima Studios about using a zk layer for games, and for more details about how we'd leverage Zeko, I'd highly recommend you take a look at it: https://blog.paimastudios.com/paima-zk-layer/

Additionally, as mentioned in a previous response, some of the details for using MINA as the interaction layer (as opposed to an EVM like Arbitrum) will depend on the progress Paima has with their cohort 3 proposal. But at the very least, I do plan to have tournaments that use MINA tokens as entry fees and do payouts directly on MINA. To refresh, tournament mode is going to be a game mode where players have to deposit a token fee to enter the "Tower of Greed," once inside, the players fight each other until only one player stands. Upon winning, this player gets to redeem the tokens of the losers. For example: 5 players enter a tournament and each deposit 2 mina. They play the game until one player remains, who gets rewards the sum of 10 mina for winning. Paima Studios has plans to make this kind of implementation more streamlined through their Paima Engine, but of course if that doesn't work out, I'd go forward with doing it myself. In the meantime, given the significant liquidity pool and mindshare of EVM compatible chains like Arbitrum, incorporating this functionality on this front would garner more users overall. 


## I would like to get more information on your go-to-market strategy. How are you planning to acquire new users? How are you going to launch the game? How are you going to get to 1000 daily users? I think an organic growth-based strategy will involve less risk.

I have a few ideas. 

## In your problem statement you are mentioning that you want to build a game that does not advertise crypto as its most valuable feature, yet it just happens to use blockchain tech in the backend. But your revenue generating strategy is heavily crypto related (in the web2 gaming space, can you name an example where the player has to lock in +$2,000 to play a newly released game, yes you do have other options, but I would say this is not a traditional gaming revenue strategy). I think this is contradictory.


## I would argue that gaming is popular, but not one of the biggest and most popular industries in the web2 world (such as e-commerce, gambling, social media, search engines, entertainment, and advertising). Do you have any data to sustain your argument?


## I would like to see a risk mitigation strategy.


## I would like to see the team info section completed.


## What is your value preposition? What is unique about your game? If you want to bring non-blockchain people to the blockchain gaming industry, you will be competing with web2 games. I would like to see more quantification over your unique selling point.
