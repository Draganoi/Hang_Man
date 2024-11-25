#Hangman
import random
import string
import requests

#importing dataset of random words
word_site = "https://www.mit.edu/~ecprice/wordlist.10000"
response = requests.get(word_site)
words = response.content.splitlines()



retry = True
wincount = 0

while retry == True:
    
    #Initial Conditions
    retry = False
    currentword = []
    win = False
    lose = False
    life = 10
    
    #Choosing a random word from the list
    randomword = words[random.randint(0,len(words)-1)]
    randomword = randomword.decode("utf-8")
    print(randomword)
    
    #Generating True/False Table
    for j in range(len(randomword)):
        currentword.append(0)
     
    #Letting player know how many letters are in word
    for n in range(len(randomword)):
        print("_", end = "")
    print("\n")    
        

    #Actual game while the player hasn't lost yet
    while (win == False) & (lose == False):
        #Setting up variable for loop
        win = True
        wrongflag = True
        printedstring = ""
        
        
        #Checking to see if the input is only 1 letter and not a special character
        guess = input("Guess a letter: ")
        while (len(guess) != 1) or (not guess.isalpha()):
            print ("Please enter only 1 letter: ", end = " ")
            guess = input()

            
        
        
        #Checks if letter is in word and mark the appropriate location to be a "1", and if it found it, then the guess isn't wrong
        for i in range(len(randomword)):
            if guess == randomword[i]:
                currentword[i] = 1
                wrongflag = False
        
        
        #Creating the string that we will show player
        for j in range(len(currentword)):
            if currentword[j] == 1:
                printedstring += randomword[j]
            else:
                printedstring += "_"
                
        
        #Checking if the player had lost
        if wrongflag == True:
            life -= 1
        if life <= 0:
            lose = True    

        #Returning Current State of the game
        print(printedstring)
        print("Life Left: ", life)
        
        #Checking Win Condition which is when all value of currentword is set to 1 (which is not 0)
        for k in range(len(currentword)):
            if currentword[k] == 0:
                win = False        
        print("\n")            
    
    
    #End Conditions
    if win == True:
        print("You Won! The word was: ", randomword, " and your win count is: ", wincount)
        wincount += 1
    if lose == True:
        print("You Lost! The word was: ", randomword)
        wincount = 0
    
    
    #Allow for player to start over or stop playing
    inputretry = input ("Do you want to play again? Y for yes and N for no: ")
    inputretry = inputretry.upper()
    inputcorrect = False
    while inputcorrect == False:
        if inputretry == "Y":
            retry = True
            currentword = []
            win = False
            lose = False
            retry = True
            life = 5
            inputcorrect = True
        elif inputretry == "N":
            print("Thank you for playing :)")
            inputcorrect = True
        else:
            inputretry = input("Please type Y for yes or N for no: ")
