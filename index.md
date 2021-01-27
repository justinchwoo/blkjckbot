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

### 29/12/2020 - Abbreviated update
Current work:
Tried to work the split strategy into the code, struggled a bit with assigning different hands and identifying the conditions of a split. The tough part was with the double digit ranks and trying to figure out the minimum amount of steps to identify a match. identifying the first and 2nd digit of each string would take at least 4 if statements if identified separately, so through lots and lots of deliberation and through drawing a new diagram (identify split.drawio) I figured out how to identify a split with 1 nested if and only having to perform a split operation in one part of the code, hopefully making developing more splits and processes on top more simple! ^^ I will post the results on /split. One more issue I had was with adding to single item string lists. I struggled to get the string list to show up as a list and after some extensive googling I figured I'll just pop some [] on the variable var(y) = [x] and give it a shot and it worked! Trial and error I guess! ^^' So that's solved as well and I have a function that identifies a split situation and a function that can split one hand into two. Next step is to modularize it so I can run up to 4 splits (or up to 6 with multiple decks of cards) without adding too many lines of code. 

Notes:
Added identify split.drawio
Added split to the list of programs
Added player_hands - a list to keep track of all the hands the player has

### 30/12/2020 - Abbreviated update
Current work:
Modularised the split, found a solution that utilises an index and finding the length of the "player_hands" list to make the code be able to identify a split wherever it is in the deck, with the player able to choose to split or not. Worked out that the double-down and the insurance bet should be placed after the split, or maybe I will implement an option where the player gets to choose their action before the split is calculated. I think the former would be simpler to code and would not change the game at all. This will involve placing new player elements, like a player_bet and a player_balance system. I have chosen to give the player the minimum bet so they don't "run out", but limits their strategy choices enough to hinder players who take bad risks and bank on the per-game income. It will take a little bit of work integrating that into the system indeed, but looking forward to working on that tomorrow and in the new year!

Notes:
Added to /split
- new code enabling the split choice to be given to players until the players choose to not split

### 14/01/2021 - Big Update
I've gotten the basic modules completed and I am trying to put the program together Building the current program gets more complicated with every additional step, and it's becoming more and more apparent that my program has a really rigid sequence and it takes agency out of the hands of the player, making playing it seem like doing a to-do list instead of actually playing it. It also makes changes difficult because every change I make has ramifications later on in the program, making changes complicated. The core issue is with the active_hand and as an extension the player_hands. I need to reconsider the way I approach constructing the data knowing what I know now: that I need to think of it as an object and figure out what attributes I would like to give it. So I'm going to work on redesigning the player_hand as an object from the ground up. Player_hands as a set is relatively straightforward as a global variable, as it contains the different hands and there really isn't much change to that variable as a whole. Now considering each hand within the player_hands set. 

Each hand would contain the following:
A SET of STRINGs denoting the cards in the hand in question

Each hand would need to be defined by the following:
Double Down Identifier - BOOLEAN this would help me in limiting draws i.a.w. the double down rule
Split Status - STR identifier (3 states) that would determine if it is awaiting process (modifying bets and balances), denied (player chose not to split) or processed/awaiting split (base status/ready state)
Bet Amount - INT representing the amount currently being bet on this hand

Will try to research ways to make this.. object or find a way to conceptually encapsulate this without resorting to spaghetti code or 4 separate sets. Current thoughts is that this would be some kind of dictionary with the key and the element that the key represents, will do some research to see if I can make that happen.

### 27/01/2021 - Big Update
I've run into quite a few issues while converting things into class form. After a few tries the class form worked, giving me a basic class for a certain card with its rank, suit and score, simplifying the ace calculation. However, as I started coding the Hand class, things started to get a little out of hand. I knew what each process did but not how a user would approach the order of processes and when each action could be taken. I haven't had a personal experience playing the game at all, and websites varied in definition and answers were nebulous and would always lead to gambling sites. At the same time the Hand class started to get more and more complex with me moving most of my modifications within the Hand class, an oversight on my part in retrospect, but it started to grow far too complex that it would take sometimes hours of googling before I could even get to work conceptualising my code, let alone write it. After around half a week of being grounded on my current step, I have decided to take a break, as for a 2nd project, I was coding something far too complex for my mind to grasp without playing the game, a game which I only wanted to recreate as websites said it would be a "good" program to start with. My primary mistake I think was building it based entirely around the user experience. Every time I found out something new about the game a large portion of the code would have needed to be rewritten, because what I built did not let me build the user experience I wanted into the game, and so every new rewrite of the code got messier and messier and more complex until this latest rewrite, basically rewriting everything in favour of class-based programming to give the user agency of what strategic action to take at a point in time, on strategy permutations I had no idea about. 

I think looking back on what I've worked so far I learned I should code just beyond my means and not FAR beyond it, and try to understand what I'm trying to do (simulate/create) before writing it out in code. I have a coding course starting today, giving me less time to code my own projects, but I am working on a new project and am going to try to display it better on github. The new project is a RNG event battle royale for discord, with no user controls. Merely a text-based adventure with a few twists in between. I will document it further on /HGbot, see you there! Or in another case, see you back here when I decide to continue! 


