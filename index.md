#Welcome to my blog recording the learning process of making a discord bot/independent program for blackjack! This is a hobby/learning project, my second python project ever and second coding project in any recent memory, designed for me to learn the thought processes and basics of coding through pushing the boundaries of my knowledge and constant problem solving (i.e. ramming my head against the wall then googling how to break it) ^^' I'm new to blogging and coding so forgive me if I miss some conventions, make mistakes and generally bumble around in code or in blogging haha

#Blog contents
### Introductory Post 24/12/2020
First post incoming just to write down the progress of the project and background so far. Roughly 1 week ago I finished coding my first full program with Python, a [quadratic formula calculator](https://github.com/justinchwoo/quadcalc) that takes a quadratic formula in the order ax^2 + bx + c = 0 and produces a discriminant and the possible solutions for x. I've only coded in the distant past in middle/secondary school, in Pascal (simple quadratic formula calculator which was the inspiration for my first python project!) and after that in Computercraft (basically pulling/modifying github code to make turtles dig stuff for me). To stretch my coding legs I also added a login and password, added a validity check using try_except_, and used while loops to keep the program running or pause a process until the user was ready. I also then revised the code, turning longer stretches of code into functions to see if I could spot inefficienties and make them better. Now I've been on this new project for roughly a little over a week. For this project, to make messing with each separate process of this program easier (anticipating an absolute avalanche of bugfixing) I have broken down the code into several independent scratchfiles to make it easier to build the processes and organise it in my brain. The efforts are split into several sub-sections as of currently:
- Login (Complete)
- Card shuffler (Complete)
- Card rank checker
- Ace score calculator (checking if the program should convert aces)
- Score calculator (checking for blackjack or bust)

Future functions that I need/want to add to the program
- Sign-ups
- Discord integration
- Split hand function (providing functionality of splitting 2 player hands)
- Player "cash" reserve
- Bid selection
- High score and leaderboard
- Stat crunching (W/L, W%, efficiency rating)
- Time-out (for discord UX, preventing an afk player from hogging the bot)
- Multiplay (several users vs dealer at once)
- GUI (?)

Thank you for stopping by! I hope you enjoy reading through my trials and tribulations and feel free to contact me through here (idk how yet I'll figure this out in time ^^'). For now I will leave this list here, update it when I can and get back to coding and googling! hahaha

### 24/12/2020 - Abbreviated update
Current Work: 
Split scoring test into 3 sections vs the original 5, removed ace calculations to a different section, as aces need to be calculated differently. Checked scoring otherwise and it works as intended so far. 

Notes: 
To keep track of scores I think we need 3 different counters to keep track of the game for each player:
- player_score - Keeping track of the total score of the player 
- player_ace_count - Keeping track of how many aces we have in the hand
- player_score_added - Keeping track of the scores added the current round (minus aces)
- player_ace_added - Keeping tack of the scores added by the aces in the current round (maybe there is a way to make this obselete)

### 26/12/2020 - Abbreviated update
Current Work: 
Changing the concept of the program, tackling the probabilities and saving the score seems hard to conceptualise and seems very confusing. How does a human approach figuring out a score in the game of blackjack? Not via looking at the score at a whole but looking at the CARDS. Will add a new list for each possible player via the list 'Hand', giving each player an actual hand they can view and that the program can run a score calculation on. Created my first flowchart to help me make sense of what decisions I might need to make, saved in the repository via diagrams.net.. I hope it works hahaha

For now I've compiled my creations so far to create a program (with defined chunks of code) that shuffles the deck, draws a card and returns the hand and the score, and put it as blkjckbot_alpha. Will keep building out the process just to get a good picture of how it works then further section off more code into functions to minimise complications. 

Notes:
Variables changed: 
- player_hand - New variable: 1 variable only for all players
- active_deck - New variable to represent the active deck being played right now
- current_draw - The current card being drawn from the deck
I will need a variable that tracks the status of the game and maybe one that decides whether or not the player draws or stands

### 27/12/2020 - Abbreviated update
Current work:
Game process basically complete! Program draws cards, assigns card to dealer hand, then draws twice for player, then proceeds to complete the game, including 2 options for the player to stay or hit, and making the dealer draw until 17. Now moving to implement the different available strategies available to the player: split, double, surrender, insurance. Will start with split, the first step would be making the processes behind draw/busting each hand modular, to make it easier to expand towards 2 decks. The inputs to the function should include, but not be limited to:
- player_hand - should now be split into hand 1 and hand 2, and a card added to each
- dealer_hand - for display to the player
- deck - to draw cards from

the function should return
- player_hand - to provide something for the dealer to play against
- player_status - to provide something to show if the player went bust

we should need a 3rd variable as well, as status can't envelop all the decision making markers PLUS whether or not the player wins or loses
- player_strategy - to provide a variable to keep track of the players' decisions

Notes:
Alpha version updated
