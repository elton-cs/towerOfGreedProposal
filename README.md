# TOWER OF GREED
Turn Based Battle Royale built with Paima Engine


## Elevator Pitch

Do you like turn-based rpgs? Do you like action-packed battle royales? Enter, Tower of Greed. A game that fuses the two genres while being powered by DeFi and zero knowledge cryptography. ToG takes skill, precision, luck, and most of all, GREED (in moderation) to win. ToG uses major technology stacks from various ecosystems to power a fun game that creates a seamless connection between crypto and gaming. ToG leverages Paima Engine to create isolated and modular sovereign game rollups, Zeko L2 to build recursive zero knowledge proof-based game instances, and Arbitrum to bring liquidity and Defi into the mix!   

## Lore
In the Tower of Greed, 5 dare to enter, and only one makes it out. Players have to fight their way to the top to reach the treasure, the almighty Greediamond. They say that whoever possesses it receives good luck and great fortune, and their names go down in history. Oh and btw, watch out for lava!

## Gameplay Overview

ToG is a 5 player battle royale where each player takes turns to move/attack in the arena, with the objective to climb up the tower while defeating the other players in the process.
Players can lose by either dying to another player, or getting consumed by the chasing lava. The last man standing wins.

Game Flow Chart:
Each game consists of 3 major components: Player Acton, Tower Action, and Round.

1. Player Action: 
- Each player in the game can perform 1 action every round.
- A player action consist of a movement, attack, or both.
  - 1. Movement only: A player can move 3 blocks in any directon
  - 2. Move and attack: A player can move 1 block in any direction and perform 1 attack.
  - 3. Attack only: A player can perform 2 attacks.
- Movement always takes precedence over an attack.

2. Tower Action:
- At the end of every two rounds, the tower can perform an action
  - 1. Feeling Cool (Gracious): The tower creates random spots of healing, when players stay in them or move into them, they get healed for some hp.
    Happens 30% of the time.
  - 2. Feeling Cruel (Gruesome): The edges of the tower get engulfed in lava. If player stay towards the edge of the arena towards 
    the end of round 2, they take 30% of their max hp as damage.
    Happens 70% of the time.

3. Round: Basically one "tick" of the game. All players make their actions during every round. The tower makes its action every 2 rounds. 

--------------------------------------------------------------------------------------------------------------------

## Proposal Overview / Summary

### Describe the problem that your zkApp is solving
Gaming is one of the biggest and most popular industries in the web2 world, and it is often touted as THE most promising avenue to bring crypto and blockchain technology to the masses. However, the negative connotations that came from the last bull market cycle's misuse of NFT technology caused many gamers to have a strong distaste for cyrpto in general. Your average CSGO, Pokemon, Fortnight, or League of Legends gamer simply doesn't care for another 10,000 unique pfp NFT collection, and many aren't willing to invest or speculate in such trades. 

The way we bring gamers into the space, is by building a game. A REAL GAME. A game that's fun and engaging, and doesn't advertise crypto as it's most valuable feature. We need a game that's straight up addicting to play, and just so happens to use blockchain technology in the backend. The game comes first. The crypto features are a bonus.

The Web3 games we have today have one major flaw. They appeal to crypto natives. Not gamers. They advertise Defi, NFTs, Tokens Airdrops, but they lack a fun and engaging game. And this needs to change if we hope to onboard the next million gamers into the ecosystem. 

### Describe your proposed solution
Tower of Greed is a game aims to do just that. ToG focuses more on building a fun and memorable game, one that's rich in art, music, game design. Specificically, ToG combines the rpg and battle royale genres to build a very unique and attractive game that's never really done before in both the crypto and general gaming spheres. The way we attract gamers is by building great games. And building great games means creating something unique. Another Call of Duty or Pokemon clone won't impress gamers, and genre mixing is the appraoch we take.  

## Architecture

### Provide technical detail for your zkApp design

Lore:

In the Tower of Greed, 5 dare to enter, and only one makes it out. Players have to fight their way to the top to reach the treasure, the almighty Greediamond. They say that whoever possesses it receives good luck and great fortune, and their names go down in history. Oh and btw, watch out for lava!

Game Design:

ToG is a 5 player battle royale where each player takes turns to move/attack in the arena, with the objective to climb up the tower while defeating the other players in the process.
Players can lose by either dying to another player, or getting consumed by the chasing lava. The last man standing wins.

Each game consists of 3 major components: Player Acton, Tower Action, and Round.

1. Player Action: 
- Each player in the game can perform 1 action every round.
- A player action consist of a movement, attack, or both.
  - 1. Movement only: A player can move 3 blocks in any directon
  - 2. Move and attack: A player can move 1 block in any direction and perform 1 attack.
  - 3. Attack only: A player can perform 2 attacks.
- Movement always takes precedence over an attack.

2. Tower Action:
- At the end of every two rounds, the tower can perform an action
  - 1. Feeling Cool (Gracious): The tower creates random spots of healing, when players stay in them or move into them, they get healed for some hp.
    Happens 30% of the time.
  - 2. Feeling Cruel (Gruesome): The edges of the tower get engulfed in lava. If player stay towards the edge of the arena towards 
    the end of round 2, they take 30% of their max hp as damage.
    Happens 70% of the time.

3. Round: Basically one "tick" of the game. All players make their actions during every round. The tower makes its action every 2 rounds. 

Development Tools:
Godot Engine: will be used to build the front end of the game. This includes game visuals, user interface, music, art, etc.

Paima Engine: will be used to build the back end of the game. This includes the bulk of the game logic, game state machines, state transition functions, database nodes, etc. Paima engine will also be used to allow interoperability between relevant chains and l2s. Primarily Mina L1, Zeko L2, and Arbitrum L2. 

Mina L1: All game results will be stored on Mina. Wins, losses, rank etc.  

Zeko L2: Primarily used to spin up game instances. Leverage recursive zk proofs to create games that don't require signing after every transaction. Allows for running many games in parallel. 

Arbitrum L2: Leverage large liquidity and user base as the game's initial player base. Implement stake-to-play model. Players can spend tokens on chain to fund the tournament mode of the game.

See Github repo for more details: https://github.com/elton-cs/zkignite3-ideas/blob/main/Tower%20of%20Greed.md

## Go-to-market strategy

### Share your go-to-market strategy, which includes:
Leverage Paima engine to bring more adoption across as many EVM chains as possible, starting with Arbitrum.
Leverage Stake-to-play model as a low risk option to invest and try the game without forcing users to feel the need to FOMO into an NFT collection.
Use stake amount tiers to provide benefits to people who are interested in the game during the early development stages. For example:
- 0.01 ETH buyers of the game get early access as well as special in-game items
- 0.1  ETH stakers get points and will be eligible for future token air drops
- 1    ETH stakers get the chance to participate in the first major ToG prize-pool tournament  


### What does success look like in terms of user adoption in 6 months from now? Please be as specific as possible.
- $1,000,000+ TVL Staked for the game (if Blast's multisig wallet can get 1 Billion+ TVL...)
- 10,000+ Active Monthly players/stakers
- 1000+ Daily Active players
- 200+ Games per day (1000 players each play one game a day = 1000/5*1 = 200)
- 1000+ members on ToG discord community

## Commercial vision

### Share your thoughts on generating revenue over a longer time horizon (greater than 6 months)
Three four avenues for revenue, as hinted above, based on the spectrum of current crypto users in the space:
1. 0.01 ETH: Buy option for those with low capital. Spend the amount to buy a copy of the game. Includes full access to the web2 version of the game, that does NOT include any crypto rewards during normal matches. However, these user will be eligible for certain ToG sponsored tournament events (maybe monthly/bi-monthly). Full amount goes to treasury. 
2. 0.1 ETH: Stake option for those with medium capital. Stake this amount to get access to the game. Includes full access to both the web2 and web3 versions of the game. Web3 version of the game includes limited number of matches per day that have crypto rewards (for example, free entry to 10 matches per day). After limit is reached, users need to spend the entry fee per game. Stake residuals flow to the treasury. 
3. 1 ETH: Stake option for those with large capital. Includes full access to both the web2 and web3 versions of the game. Much higher free entry limit compared to previous option (maybe even unlimited free access depending on revenue to fund game tournaments). Stake residuals flow to the treasury. 
4. 0.001 ETH: Entry Fee for single ToG tournament game (tournament game implies a token prize pool for winning). 


### What is your long-term vision for this project if your proposal is funded? What is your dream scenario for how this project could evolve?
Continue building the project till it reaches $100,000,000 TVL. 
After which, partnering with an established game studio IP would lead to massive adoption from the web2 ecosystem. 
Blazblue, an Arc System Works IP, is where I'm looking at first. They've built popular games like Guilty Gear Strive and Dragon Ball Fighterz, However, after their last Blazblue fighting game (Central Fiction) in 2015, they've run into trouble developing a popular successor to the franchise, and have gone stagnant since.
Their last attempt was a turn based gatcha style game (BlazBlue Alternative: Dark War) on mobile that flopped and died one year after release.
Lastly, they very recently partnered with another indie studio to build a game based on a different genre (Blazblue Entropy Effect), which was mildly successful, which leads me to believe they'd be open to doing it again if a game shows promise.

Ideally, partnering with an established, name brand IP, is the best way to garner growth and generate interest from the gaming community.

## Budget and milestones

### Standard Budget Proposal
(Required) The standard scope is the minimum budget, scope, and milestones which can be delivered in the proposed three month development sprint.

Standard Budget in MINA
30000

### Standard Scope
Front End - 10000
Paima Engine Backend - 10000
Zeko Game Contracts - 5000
Arbitrum Contracts - 5000

### Standard Scope Milestones
Complete the web2 version of the game within the half way point. The entire game without any of the crypto and staking features. This allows for play testing and more iterations in the design of the game while working on the crypto backends.

Complete the web3 version of the game by the end of the cohort. Plug in all the crypto options into the game to make it a fully fledged web3 game powered by crypto.

### Advanced Budget Proposal
(Optional) The advanced scope section allow you to propose a larger scope and effort for the same development timeline. The advanced scope will replace the standard scope if the funding target is met. As a replacement to the standard scope, you would still document the original budget, scope and milestones AND add the additional budget, scope, and milestones to present a TOTAL proposal which could be delivered in the proposed three month development sprint.

Propose Advanced Scope?
No

## Risks & Dependencies

### What risks or dependencies do you foresee with building and launching this application?

Paima Engine is a relatively new game engine, that started around 2 years ago.

Zeko is also being actively developed. Currently not even released to the public yet.

Arbitrum has not incorporated fraud proofs yet, so there's a centralization risk there.

### Team Members

Open to working with 1-2 team members. 

Member needs to be strong in either game development (Unity, Godot, Bevy) or strong in Mina and/or Ethereum smart contract development (mina navigator or previous cohort member highly preferred).