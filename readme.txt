
This corpus contains 29,913 games of 13x13 Hex scraped from Little Golem (http://littlegolem.net/) on April 17, 2016. I used this data set for an undergraduate AI research project. When I began the project, I was surprised and disappointed by the lack of free Hex data sets online, so I decided to make my data public to save future researchers the hassle of scraping. If you notice any issues with this data set, please contact me at jlp353 (at) cornell (dot) edu.

The header in corpus-final.txt explains its format:

# One Hex game per line.
# line =  <game id> <player1 id> <player2 id> <winner id> <resignation> <move1> <move2> ...
# <winner id> = ID of the player who won
# <resignation> = True or False (True iff the game ended in resignation, not a full win)
# <move> = row:col, "swap", or "resign"
# player1 always goes first and plays from top to bottom on the board.

row:col tile indexing works as illustrated in this 4x4 example:

      0 1 2 3
    0  . . . .
    1   . . x .
    2    . . . .
    3     . . . . 

So the 'x' on the board is at position 1:2.


Other notes:
- As you'll notice, most games end in resignation, even long ones. This is probably because skilled players can see at least few moves in advance when they've made a fatal mistake.

- The scraper should have seen every game initiated through April 17, 2016, including those games still in progress. However, the corpus excludes games that were not completed -- i.e. nobody won and nobody resigned.

- All completed games (i.e. somebody won or resigned) are included regardless of length. For example, if a player resigned two moves into the game, it's still included, even though the resulting "win" is probably statistically meaningless. I leave it up to you to set a minimum game length.

- All games are played with swapping (pie rule) allowed. Obviously, you can filter out games in which swapping occurs and treat the resulting corpus as one with swapping disallowed. 

- On Little Golem, players are assigned a rank for each game variant that they play. You might find this info useful for ML purposes. Unfortunately, I didn't scrape it, but you have all the player IDs and could write a trivial scraper to fetch their ranks.

