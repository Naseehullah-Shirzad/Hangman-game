# Hangman-game
This is a fruit guessing game with new features
from random import choice
print('welcome to the fruit guessing game!!!')
while True:
    fruits = ['apple', 'banana', 'melon', 'peach']
    fruit = choice(fruits)
    hidden_fruit = ['_'] * len(fruit)
    print(hidden_fruit)
    wrong_guesses = 0
    max_attempts = 5
    incorrect_guesses = []
    while wrong_guesses <= max_attempts:
        print('word to guess:', ' '.join(hidden_fruit))
        print('incorrect guesses', incorrect_guesses)
        letter = input('Enter the letter')
        if letter in fruit:
            for i in range(len(fruit)):
                if fruit[i] == letter:
                    hidden_fruit[i] = letter
        else:
            incorrect_guesses.append(letter)
            wrong_guesses += 1
        if '_' not in hidden_fruit:
            print('Congratulations! you have guess the fruit', fruit)
            break

    if wrong_guesses >= max_attempts:
        print('Sorry! you have lost. the fruit was: ', fruit)
    choosing = input('Do you want to play again: ')
    if choosing == 'yes':
        continue
    else:
        break
