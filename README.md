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
  * all players in the squad \<Vector\<Player>>

* SquadList struct with fields for 

  * SquadList creator public key <Pubkey>
  * all squads in list \<Vector\<Squad>>

* Methods for 

  * creating a squad
  * updating a squad (squad creator only)
  * deleting a squad (admin only)
  * creating a player
  * updating a player (player can change squad, admins and authorized programs can change player's score)
  * deleting a player (admin or player only)

## TODOS LEFT FOR ME:

* Onchain voting program
  * Interpret results so players can get paid out... use Helius webhook? 
* Twitter integration (Auth0)
* Ideally pull data with Helius Webhooks
* Create client side methods for
  * Admin:
    * Create games
    * Manage game
    * You know, maybe I should just use SOAR for this. That might make more sense. And then do some kind of CPI call to my main program?
  * Player:
    * Create squad
    * Join squad
    * Join game (onchain voting program)
      * Pay a little BONK for prize pool (so, need a vault for that)
      * Winner gets paid out at the end of the month
      *     
Maybe I should just have the onchain voting program use SOAR? I guess I could do a CPI call for that?

That's probably more than enough for getting done by Sunday. 


