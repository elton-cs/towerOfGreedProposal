# Zeko Architecture

## Overview

Each game instance of Tower of God (ToG) will run on a Zeko instance. 
This means that one instance is spun up for every 4 players that queue up for a match.
Once the game instance launches, players send moves to the instance, which gets processed similarly to Mina account updates and recursive proofs
Once the game ends, and the results are available (aka who won, lost, and other game stats like exp, damage dealt etc.),
The Zeko instance is rolled up and a proof of the game is posted to Mina. 

In this section, we'll delve deeper into the Zeko architecture

## Zeko Flow

### Game Setup
1. After 4 players have queued up to start a ToG session, a Zeko instance is spun up to begin the game.
2. Each player then sends a transaction to certify they are ready to start the game and sign with their unique session key.
3. A single zk proof (GameStartProof) is then generated with data that represents the following:
    1. Initial map size
    2. Initial map shape
    3. Player starting positions (from identifiers collected prior)
    4. Player starting stats like health, statuses, attack modifiers etc. 
4. A copy of GameStartProof is sent to each of the players to verify and proof is posted onto Zeko 

### Game Rounds Begin
5. Each player makes their move and sends them to the Zeko instance as a transaction.
6. After all 4 players make their move, the game node processes the Paima game state, and posts the new changes of map and player attributes to the Zeko
7. These two main processes loop until one player remains

### Winner Claims Reward
8. Final game state concludes in Zeko, which is then rolled up and posted as a single proof unto Mina
9. Winner runs claim() function on Arbitrum
10. claim() uses lambdaClass zkBridge to get Mina state, verifies information, and releases reward to winner


On chain State:
5 Fields, each being a hash of the player's location