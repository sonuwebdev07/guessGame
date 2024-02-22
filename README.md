# guessGame
import random

randNumber = random.randint(1, 100)

userGuesses = None
guesses = 0
while(userGuesses != randNumber):
    userGuesses = int(input("Enter Your Guess : "))
    guesses += 1
    if(userGuesses == randNumber):
        print("You Guess it Right !")
    else:
        if(userGuesses>randNumber):
            print("You Guess It Wrong ! Enter a smaller Number : ")
        else:
            print("You Guess It Wrong ! Enter a Larger Number : ")

print(f"You guessed the number in {guesses} guesses.")

with open("highscore.txt","r") as f:
    highscore = int(f.read())

if(guesses<highscore):
    print("you just broke the high score ")
    with open("highscore.txt","w") as f:
        f.write(str(guesses))
