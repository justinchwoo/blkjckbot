#Welcome to my blog recording the learning process of making a discord bot/independent Bprogram for blackjack! This is a hobby/learning project, my second python project ever and second coding project in any recent memory, designed for me to learn the thought processes and basics of coding through pushing the boundaries of my knowledge and constant problem solving (i.e. ramming my head against the wall then googling how to break it) ^^' I'm new to blogging and coding so forgive me if I miss some conventions, make mistakes and generally bumble around in code or in blogging haha

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
