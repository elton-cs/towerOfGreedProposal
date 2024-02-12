# PROPOSAL REVIEW

<!-- Robin Sarfati -->

## Do you have details on the team ? are you related to the builders of Paima / zeko ? Also I am not sure to understand the role of arbitrum in the proposal it seems to engage users, in the githu I see the entry fees for the game in MINA token. Also arbitrum integration wouldn't be in the standard scope, am I understanding it right ? 

Hey there! Thanks for the questions.
1. I’m currently a one man team. I’ve been active around the discord but I haven’t had anyone reach out to collaborate yet, so for the time being it’s going to stay a solo project, which is fine by me. My plans for working with a team is probably going be to getting some active Mina navigators to help contribute, and I’ll do so with some of the funding I receive.
2. I am not related to the builders of Paima or Zeko, just an enthusiast of their tech stack and vision. I’ve been researching them since they announced their ZK layer blog back in December (https://blog.paimastudios.com/paima-zk-layer) and I’ve really delved deep into their ecosystem to learn and I’m ready to build.
3. The entry fees were initially denoted in MINA but will probably change to ETH on Arbitrum. Also the Arbitrum implementation is still a work-in-progress and depends on a few factors. (1) Paima is also proposing some useful features to implement Mina interoperability with Paima during this cohort, and a lot of their features can and will be used with Tower of Greed. What they build and get funded for will impact the work I need to do to incorporate ToG with Mina. If there’s more Mina Paima primitives being built out by the Paima team, there will be more Arbitrum features I can add to the standard scope. (2) So with that in mind, I’m currently shooting for using Arbitrum for the entry fees for the game, and use Mina to store the Zeko rolled up game state instances. In this scenario, the fees will be denoted in ETH. But again, this is subject to change over the coming days.

If you’d like to see more info on the project, please follow this github repo as well: https://github.com/elton-cs/towerOfGreedProposal

Thanks for your questions!

<!-- Nicolas Manea -->

## 1. I would like to understand a bit more about the requirement of using MINA in your project. Please further explain why MINA.

The main reason for choosing MINA over other platforms for Tower of Greed is to leverage MINA's recursive zk proof system to create scalable game instances. When playing ToG, players send actions, like moving and attacking, in parallel. Because of this, these actions are private inputs that cannot be sent as open and public transactions to a typical blockchain functioning as a public ledger. To solve this issue of having a game require secret inputs WHILE NOT relying on a trusted third party (which is how games are usually built in a server model), we use MINA's smart contract and zkprogram libraries to build the game. More specifically, this will be done by using Zeko L2 instances, which would be faster and provide more throughput for individual game instances while not depending on a centralized game server to act honest. Instead the game node will be responsible for proving the user's inputs and creating recursive proofs that contain the state of the game over time. 

ToG is heavily inspired by the proposed model written by Paima Studios about using a zk layer for games, and for more details about how we'd leverage Zeko, I'd highly recommend you take a look at it: https://blog.paimastudios.com/paima-zk-layer/

Additionally, as mentioned in a previous response, some of the details for using MINA as the interaction layer (as opposed to an EVM like Arbitrum) will depend on the progress Paima has with their cohort 3 proposal. But at the very least, I do plan to have tournaments that use MINA tokens as entry fees and do payouts directly on MINA. To refresh, tournament mode is going to be a game mode where players have to deposit a token fee to enter the "Tower of Greed," once inside, the players fight each other until only one player stands. Upon winning, this player gets to redeem the tokens of the losers. For example: 5 players enter a tournament and each deposit 2 mina. They play the game until one player remains, who gets rewards the sum of 10 mina for winning. Paima Studios has plans to make this kind of implementation more streamlined through their Paima Engine, but of course if that doesn't work out, I'd go forward with doing it myself. In the meantime, given the significant liquidity pool and mindshare of EVM compatible chains like Arbitrum, incorporating this functionality on this front would garner more users overall. 


## 2. In your problem statement you are mentioning that you want to build a game that does not advertise crypto as its most valuable feature, yet it just happens to use blockchain tech in the backend. But your revenue generating strategy is heavily crypto related (in the web2 gaming space, can you name an example where the player has to lock in +$2,000 to play a newly released game, yes you do have other options, but I would say this is not a traditional gaming revenue strategy). I think this is contradictory.

I'd like to address this question first before I talk about my go-to-market strategy. Upon first glance, I'll admit it does seem contradictory, but I hope I can provide more information to convince you otherwise. 

First thing, Tower of Greed is going to be built as two separate game versions (or "editions" if you will): 
1. Standard Edition (Web2)
2. Crypto Edition (Web3)

Both versions of the game will come with the base gameplay and mechanics. This includes the standard 5-player mode. There is no entry fee, players fight each other in the Tower of Greed, and the last man standing wins. Winner gets exp to level up their character, which will eventually be used to create a leaderboard (and in the future, a ranking system).

The Standard edition of the game is what I alluded to when I mentioned that the game doesn't advertise crypto as it's most valuable feature. Tower of Greed can be enjoyed by the casual gamer on it's own without having to know anything about, or interact with, crypto. This is what I mean building a game that's fun to play first, but can be enhanced by crypto primitives later.

Which brings me to the Crypto Edition. This version of the game adds a layer of fun (and degen?) to the game by introducing DeFi into the mix. Major additions to this version of the game include:
1. Stake-to-Play model: In order to play the crypto edition of the game, the first requirement is to either stake a token amount or buy the version with crypto (details in the github). What features one can get access to depends on this factor. I'm looking to stake with Compound Finance on Arbitrum and use the yield from staking to fund tournaments and give incentives to the players.
2. Tournament Mode: Players have to pay an entry fee in tokens (MINA and/or ETH) to start a ToG session. The winner gets rewarded the sum of the entry fees (minus a small percentage that goes to the treasury). The breakdown of this mode depends on what "Tier" of the game the player has.
   1. Tier I: Buy for 0.01 ETH. By doing so, you unlock tournament mode and can play up to 5 tournaments per day (Upon further inspection, I noticed that this option initially mentions NO tournament play, so you were right that it looked contradictory, I'll be fixing it later). Can also participate in ToG sponsored tournaments. This is the low capital option.
   2. Tier II: Stake for 0.1 ETH. This unlocks tournament mode and you can play up to 25 tournaments per day. On top of that, the percentage of the entry fee that you win is higher (aka less is given to the treasury). This is the medium capital option
   3.  Tire III: Stake for 1 ETH. This fully unlocks the game and all features and benefits. You can play 50 tournaments per day. The percentage of the entry fee that you win is the highest it can be, and these players get access to the special tournaments with larger prize pools funded from the revenue generated for all the user's staking. (With future plans to add even more incentives)
3.  Points. Points. Points. Last, but certainly not least. Another additional feature that I'd like to include for the Crypto Edition is a points system for more incentives. Points have been very popular recently and it's something that a lot of the crypto community is excited for. So Tower of Greed will also be distributing points to those that stake with us. We might also incorporate the use of liquid staking and restaking tokens as well, to add to the hype train. 

And this is just the tip of the iceberg. I have so many more ideas but I'm trying to keep it reasonable within the 3 month time frame.

From what I've planned so far, the stake-to-play model and the points system will be part of the Advanced Scope Track, while the regular Crypto Edition with tournament mode will be part of the Normal Scope. 

## 3. I would like to get more information on your go-to-market strategy. How are you planning to acquire new users? How are you going to launch the game? How are you going to get to 1000 daily users? I think an organic growth-based strategy will involve less risk.

Standard Edition: Follows the normal indie game timeline. Essentially using Steam as the main platform to market the game from development to launch. 

1. During Development: Indie Games tend to gain traction with things like dev-logs and teasers. So I'd like to gain traction for the game using Steam's wishlist in conjunction with trailers, teaser's and weekly (maybe even daily?) dev logs or coding streams. 
2. During Alpha/Beta: Early releases of the game will be playable to those who join the Tower of Greed Discord channel early. I'll also give incentives like random free copies of the game during pre-release. Additionally, have discounts or special items/skins for early backers. 

Just as you mentioned, for the Standard edition of the game, I'd like to have organic growth for the game. At the end of the day, a good game will bring passionate players and lead to a loyal fan base, and leveraging the Steam Store is typically the best way to go about it. 

Crypto Edition: Revolves around the point system and staking.

1. During Development: Early backers of the game can stake to earn multiplier points for believing in the project and the success of the game. These points can then either be used to redeem the game before launch or be used for other incentives (to be determined as development progresses).
2. During Alpha/Beta: Get to play test the game before it's released to the public. Players earn more points based on games played, number of wins etc. 

Here, the idea is to use staking and the point system to garner attention and hype. The goal of the points system is to eventually do a token launch or use points in a positive way to better the gaming experience. Either way, the scope of how to use points is beyond the 3 Month build phase, but it's definitely something I have in mind for the near future and I'm very open to suggestions from the community. 

Post Launch: This is going to consist of youtube videos, trailers, collaborations with Paima Studios and partners, and much more.
For the Standard edition, I'd like to plug into the Godot developers community to showcase the game built with their engine.
For the Crypto edition, it's going to consist of talks and presentations to other blockchain communities and VCs. Posting on twitter (X) and Farcaster is also something I'll be focusing on. 

This is what I have so far, but i'm sure more ideas are soon to come and I'm very open to suggestions.

## I would argue that gaming is popular, but not one of the biggest and most popular industries in the web2 world (such as e-commerce, gambling, social media, search engines, entertainment, and advertising). Do you have any data to sustain your argument?

This is a good point and it's something I'm actively researching. I suppose I should clarify my stance on the matter and say this:
While there are much bigger industries in the space, I truly believe that gaming in crypto is one of the only ones that doesn't really have a dominating winner yet. For Defi, we have lending protocols like AAVE and Compound, for AMMs we got Uniswap, for social media apps, we have Lens and Farcaster etc.

We HAD Axie Infinity for gaming, but I don't think gamers liked that one haha. While it was a major success for some time, I think many agree that the gaming aspect was very lack luster and was more of a niche and novel usage of NFTs. 

I'm aiming to be the first game that goes mainstream. Is it a long shot? yes. Are the odds in my favor? Absolutely not.

But there's a throne that's empty, and someones going to take it one day. So until that happens, I'd like to be optimistic and say Tower of Greed can get there :D

Lastly about the subject of gaming, I haven't seen any projects try to capture an established player in the space yet. The closest I've seen are some Immutable games that managed to release on the Epic Games Store, but there aren't any projects that managed to get an IP license yet.

I talked about this aspect in my long-term vision for this project, but essentially I want to partner with an established game's IP to build Tower of Greed. This, I believe, has the most promise to bring crypto into gaming. We can't hope to build a new IP that no one has heard of before, and except it to compete in the big leagues. But If we can get enough interest and attention, we could partner up with another game studio to reach new heights.

## I would like to see a risk mitigation strategy.

This is something I'm still working on. Would love to hear more advice and suggestions on this. In terms of keeping the game risk averse in relation to DeFi, one of the benefits of using Paima Engine is that it separates the gameplay from the crypto functionality. 
By being a sovereign rollup, we can iterate on game design without affecting the liquidity on chain. Additionally, by using Paima's primitive's like Projection NFTs, we can have a lot more flexibility without too much risk.  

Of course, the main tournament and staking smart contracts will have to be carefully designed and audited as it's being written, so that's something to take note of.


## I would like to see the team info section completed.

At this point, Tower of Greed is going to start as a solo project. As mentioned before, once the project is funded, I hope to incentivize current Mina Navigators to help in building the Zeko L2 contracts to speed up development. Additionally, some funding will also be used to get custom art and music for the game.  

## What is your value preposition? What is unique about your game? If you want to bring non-blockchain people to the blockchain gaming industry, you will be competing with web2 games. I would like to see more quantification over your unique selling point.

Tower of Greed is a spin on a popular game from the pokemon franchise: Pokemon Mystery Dungeon. Except, it's fully PvP.
The value preposition for the game are two fold: For casual gamers, ToG is a game that combines two unique and seemingly unrelated genres: turn-based rpg and battle royale. 
For the crypto native, ToG uses the latest technologies in the blockchain space like staking and points to create hype and bring value to the community while building a fun and enjoyable game. 

There's still more details I'll be adding to the draft, but my response is getting really big so I'll have to cut it here.

Thanks for the questions!

<!-- Rahul Ghangas -->

Great idea, a few questions that are unclear from the proposal.

## 1. I don’t completely follow how recursive zk proofs are used in the game. If you intend to use recursive zk proofs for state change corresponding to each action, action can be inferred from the final state (which is public) when a transaction is submitted. How exactly are transactions being hidden here?

One entire game session runs on a Zeko instance. There are two things that happen here:

First, the Zeko instance itself can (and probably will) be private so no player can see what another player's actions are until the entire game is over. In this case, only the game node could have access to this information, which while not ideal, is better than trusting the players to act honestly. 

Second, another layer of privacy is using o1js' zkProgram module to create recursive proofs where each player's actions are totally private and no one can tell what move's were made. In this case, the prover (the game node in this case) can only combine the players' proofs into a new recursive proof to post on the Zeko instance. When doing this, the public output can only be the state of the game on round prior (which would include things like player location, healths, etc.) Which shouldn't matter since the movement and attack options give enough randomness that inferring a player's next move would be difficult to do. 

## 2. How does interoperability between Zeko and arbitrum work? Can you explain or link relevant resources?

The following article pretty much explains the relationship between Zeko and Arbitrum:

https://blog.paimastudios.com/paima-zk-layer/

## 3. Game (including on chain) architecture and how Mina zkapps are used is still unclear, please elaborate.

I'm currently working on this to add to the current proposal. I should have a more detailed description in a little bit. 

## 4. Finally, my biggest concern is the dependency on two other nascent projects. A lot of assumptions are made w.r.t the development of both those projects, which cannot be guaranteed until someone from these projects is directly on the team to guarantee that.

So Paima Engine is fairly well established in the gaming space. They've been present for nearly two years so while there can be a concern with this dependency, the entire proposal relies on the fact that we're building a game on Paima. But in terms of risk mitigation, it's still entirely possible to build the game without it, there's just a lot of streamlining and niceties that come with using Paima Engine. 

Zeko is probably the weaker link of the two, as it hasn't been released yet. However, given that Zeko is essentially just a faster MINA but less restrictions, it shouldn't add much overhead to development. Additionally, if for some reason Zeko doesn't work as a rollup, I still Protokit as a backup that can be used to build the game. Protokit is also another rollup that's actively being developed in the Mina ecosystem, and they were a project that came from cohort 1. 

As a last resort, the game can still be built purely with Mina with most of the tournament functionality, the only thing that would not be feasible within the 3 month time frame would be the stake-to-play features on EVM compatible chains, but this falls under the advanced track and again, relies on the assumption that Paima and Zeko are functioning as intended.

Thanks for the questions!