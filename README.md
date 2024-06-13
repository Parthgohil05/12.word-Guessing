# Hangman Game

This is a simple implementation of the classic Hangman game using Python. The game randomly selects a word from a predefined list, and the player tries to guess the word by suggesting letters within a certain number of guesses.

## How to Play

1. **Start the Game**: Run the Python script.
2. **Enter Your Name**: The game will prompt you to enter your name.
3. **Guess the Word**: You will be prompted to guess a letter. You have 12 attempts to guess the word correctly.
4. **Winning the Game**: If you guess all the letters in the word correctly within the allowed attempts, you win the game.
5. **Losing the Game**: If you fail to guess the word within the allowed attempts, you lose the game.

## Prerequisites

Make sure you have Python installed on your system. This script is compatible with Python 3.

## Running the Game

1. Save the script to a file, for example `hangman.py`.
2. Open a terminal or command prompt.
3. Navigate to the directory where the script is saved.
4. Run the script using the command:

    ```sh
    python hangman.py
    ```

## The Code

```python
import random

name = input("What is your name? ")

print("Good Luck ! ", name)

words = ["algorithm","compiler","debugging","framework",
         "function","variable","object-oriented","source code",
         "syntax","loop","pointer","database"]

word = random.choice(words)

print("Guess the characters")

guesses = ''

turns = 12

while turns > 0:

    failed = 0

    for char in word:

        if char in guesses:
            print(char, end=" ")
        else:
            print(" _ ", end="")

            failed += 1

    if failed == 0:

        print("\nYou Win")
        print("The word is:", word)
        break

    print()
    guess = input("guess a character:")

    guesses += guess

    if guess not in word:

        turns -= 1

        print("Wrong")
        print("You have", + turns, 'more guesses')

        if turns == 0:
            print("You Lose")
```

## Customizing the Game

You can customize the game by modifying the `words` list to include words of your choice. Simply edit the list in the script:

```python
words = ["your", "custom", "word", "list", "here"]
```

## Troubleshooting

- If the script doesn't run, ensure you have Python installed and that you are using the correct version.
- Ensure there are no syntax errors in the script by copying it correctly.

## Contributing

If you have suggestions or improvements, feel free to fork the repository and submit a pull request.

## License

This project is open-source and available under the MIT License. See the `LICENSE` file for more information.

---

Enjoy playing the Hangman game and good luck
