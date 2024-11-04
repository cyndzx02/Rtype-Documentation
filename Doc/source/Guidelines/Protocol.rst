Protocol
********

Rtype Protocol document                                     
+++++++++++++++++++++++

Authors
=======
a. Cynthia ZINSOU
b. Hanniel DEGBELO
c. Katia ELEGBE
d. Abiola FAYEMI
e. Hermann GAGNON

Request for Comments
Title:    Rtype Protocol
Author:   Cynthia Zinsou
Date:     29 October 2024

Rtype protocol documentation: 1

  Status of the Request for Comments:
    This document presents the protocol of the both, part one and two
    of the rtype project.
    The Rtype project is basically a shooting game.
    That we reproduced using SFML library and c++ programming language.

CONTENTS

1. Introduction . . . . . . . . . . . . . . . . . . . . . . . . . 1
2. The Architecture . . . . . . . . . . . . . . . . . . . . . . . 2
3. The TCP Protocol Commands . . . . . . . . . . . . . . . .  . . 3
4. The UDP Protocol Commands . . . . . . . . . . .  . . . . . . . 4
        







   



  

1. Introduction
===============
    The main goal of this project is coding a multithreaded game in c++, which main
    aim would be a shooting game. The player could play with many players online.And
    The game should be multiplatform That is, running on windows as well as on  linux.
    And Rtype is a third year project (TEK3) at EPITECH.
    This document introduce you to the different protocol been used in the rtype project.




2. The Architecture
===================
    The project architecture follows a specific pattern known as the ECS. On the 
    other hand, lauching this game lets you to wait at a minimum of connected 
    players before letting the game starts. Still this game architecture follows
    the normal "client-Server connection" architecture. The clients connects itself
    to the Server using a given protocol. 


3. The TCP Protocol commands
++++++++++++++++++++++++++++

1. CONNECT
==========
The client initiates a connection with the server
- **Syntax:** CONNECT [USERNAME]

2. DISCONNECT
=============
The Client diconnect from the server
- **Syntax:** DISCONNECT


4. The UDP Protocol Commands
++++++++++++++++++++++++++++

1. CONNECT
==========
The client initiates a connection with the server
- **Syntax:** CONNECT [USERNAME]

2. DISCONNECT
=============
 The Client diconnect from the server

- **Syntax:** DISCONNECT

3. MOVE
=======
 The client moves the player around the window
 **Syntax:** MOVE [OPTIONS]
 OPTIONS:
 UP: The player moves to the top of the window
 DOWN: The player moves to the bottom of the window
 FORWARD: The player moves to the left of the window
 BACKWARD: The player moves to the right of the window

4. SHOOT
========
The client shoot on the ennemies
**Syntax:** SHOOT

5. DEAD
=======
 The client die during the game
 **Syntax:** DEAD [PLAYER_NUM]

6. PLAY
=======
The server sent "PLAY" command when it reached the limit of connection
**Syntax:** PLAY

7. WIN
======
The server sent "WIN" when the palyer finisgh a level (by killing the boss)
**Syntax:** WIN

8. SCORE
========
Resquest for the player SCORE
**Syntax:** SCORE [PLAYER_SCORE]

9.  CREATE
==========
The client send this request to create a game

10.  MISL
=========
The server send this request to all clients in a game part when a missile is launched
**Syntax:** MISL [x y]

11.  MISDTH
The server send this message to all clients in the game part when a missile is destroyed
or overflow the window

12.  POSITION
=============
The server send this message to update a specific player position
**Syntax:** POSITION [number x y]

13.  PLAYERS
============
The server send the name of connected players
**Syntax:** PLAYERS [number]

14.  ASTL
=========
The server create an asteroid
**Syntax:** ASTL [x y]


[RFC]                          Rtype Protocol                      29 October 2024     
