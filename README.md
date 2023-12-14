# BONKSquad

BONKSquad is a social interaction and teamwork-based game on the Solana blockchain where users can form squads and participate in social tasks to earn BONK tokens. 

## Architecture

### BONKSquad App

The BONKSquad App is a full-stack node.js app.

This GitHub repository contains the code for the BONKSquad App.

It includes

* an admin dashboard for creating and managing games
* a player dashboard for creating and joining squads and for joining games 

### Squad Log

The Squad Log is an onchain Solana program written in Anchor. 

The GitHub repository for the Squad Log is at (https://github.com/Suizzle/bonk-squad-log)[https://github.com/Suizzle/bonk-squad-log]

It includes

* Player struct with fields for 

  * player public key <Pubkey>
  * player Twitter handle <String>
  * player squad <String>
  * player score <i64>

* Squad struct with fields for

  * squad creator public key <Pubkey>
  * squad name <String, max chars 15>
  * squad logo <String - URI of logo> 
  * squad motto <String, max chars 30>
  * all players in the squad <Vector<Player>>

* SquadList struct with fields for 

  * SquadList creator public key <Pubkey>
  * all squads in list <Vector<Squad>>

* Methods for 

  * creating a squad
  * updating a squad (squad creator only)
  * deleting a squad (admin only)
  * creating a player
  * updating a player (player can change squad, admins and authorized programs can change player's score)
  * deleting a player (admin or player only)

