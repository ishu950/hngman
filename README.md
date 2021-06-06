# hngman
1
from replit import clear
import random
from randm import word_list

HANGMAN_PICS = ['''
     +---+
         |
        |
         |
        ===''', '''
     +---+
     O   |
        |
        |
       ===''', '''
    +---+
    O   |
    |   |
        |
       ===''', '''
    +---+
    O   |
   /|   |
        |
       ===''', '''
    +---+
    O   |
   /|\  |
        |
       ===''', '''
    +---+
    O   |
   /|\  |
   /    |
       ===''', '''
    +---+
    O   |
   /|\  |
   / \  |
       ===''']

print("welcome to hangman")

end_of_game=False

chose_word=random.choice(word_list)
print(chose_word)
length_word=len(chose_word)
display=[ ]
for i in range(0, length_word):
    v = "_"
    display.append(v)
count=6
while end_of_game==False:

        guess=input("guess")
        clear()
        for i in range(length_word):
            letter=chose_word[i]
            if guess==letter:
                display[i]=guess
        print(f"{display}")
        if guess in display:
            print("already there")
        else:
            print("not")

        if guess not in chose_word:
            print(f"your guesse {guess} is not in word.you lose")
            count -= 1
            if count == 0:
                end_of_game = True
                print("you loose")
        if "_" not in display:
            end_of_game = True
            print("you win")

        print(HANGMAN_PICS[count])
