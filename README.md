# Hang_Man
Recreation of the game of hang man where user will have to guess all of the letters that makes up a word to win.
The database of word which can be chosen from for this project is listed on "https://www.mit.edu/~ecprice/wordlist.10000".


After running the program, the game will print a row of lines in the terminal. These lines represent the letter that makes up the word. The program will then ask the user for a guess. If you were to type an answer that is not an alphabetical letter OR is not a single letter, then the computer will prompt the user to resubmit their guess. The way that I had used to keep track of which letter is already discovered is through a list of 1s for discovered words and 0s for those that haven't been discovered yet.

For example, for or_ng_, the corresponding list would be [1, 1, 0, 1, 1, 0]

If the guess that was made is wrong, then the lives counter would decrease by 1. The game would end if the lives counter would reach 0 or if the user had guessed all of the letters that make up the word. The user will then given the choice to type "Y" to play the game again or "N" to exit the game.

I initially wanted to take on this project to relearn python since it has been a while since I had last touch the language. There were a lot of things which I had to relearn such as how strings are indexable but NOT malleable, and things I had to learn like using the "request" library to import data from a website. Overall this project was both fun and very informative in terms of understanding Python again!
