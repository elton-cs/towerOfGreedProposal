# Mina Architecture

## Tournament Smart Contract

<!-- user decides they want to participate in a tournament -->

<!-- user deposits token entry fee to smart contract -->

<!-- after 5+ unique users deposit the entry fee, a game can be played -->

<!-- winner of the game is then the only eligible user who can withdraw the reward -->

On Chain State:
Field: MerkleTreeOfUsersWithTickets
Field: MerkleTreeOfActiveGames

buyTickets(numOfTickets): user calls this function to deposit the entry fee for a tournament, and gets a "ticket" in return. This value gets added to the on chain merkle tree. 

startGame(): ToG calls this function when it matches 5 players into a game and starts a game instance. The function commits to a valid active game that have claimable rewards upon completion.

claimReward(proofOfWinner): user calls this function after winning a game. Winner rewards are sent from the SC to the user. The proofOfWinner proof will come from the active game's Zeko instance. 