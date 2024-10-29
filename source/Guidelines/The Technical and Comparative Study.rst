Technical and Comparative Study
*******************************

This covers the relevance of using the various technologies we are employing
(programming language, graphics library, algorithms, networking techniques, etc. . . ).

The project is been asked to be coded in *C++ language* using the graphical library of 
*SFML* following the algorithm of the original *RTYPE* game logic and making it available
over the network as well.

To encompass this, let's cover up what is been done and why it's been done that way.

* **Used Algorithm**

Design patterns
================
Choosing this design patterns helps escape a lot of problems in developing our engine.
First thing is the flexibility. To solve this ECS get started with a
blank object that has only the default required to do its job.
Due to inheritance trees might get messed up. In a gameplay inheritance can cause problems.
Second thing is the misuse of the cache because in a game we interate over a set of object a 
number of time(in fact multiple times per second). And this causes a huge waste of the cache.
It's the result we get by restarting our systems or looking for alternative to cool the CPU.
To solve this our ECS would keep all the data that will be iterated upon a 
tightly packed by using the only space required for it in our cache.
To summarize it we set to design our game with these goals

#. Making our code simple and understandable for every developers
#. Avoid a lot of if conditions to help avoid misprediction
#. Have a minimal use of inheritance

Data structures for the project
===============================

*  **as well as our selection of new and custom-designed algorithms** 


Storage
=======
a study of different storage techniques should be included in our comparative study,
regarding persistence, reliability, and storage constraints.


Security
=========
security and data integrity must be managed and secured effectively.
In our comparative study, it might be relevant to consider the main vulnerabilities
of each technology. Also, explain how we implemented the security monitoring of those
technologies, in the long term.