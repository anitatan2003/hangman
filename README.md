# Hangman

In a normal game of hangman, the computer picks a word that doesn’t change, and
then the user is supposed to guess. The user guesses individual letters until the word is
fully discovered.
In thsi game of hangman, the computer delays picking a word until it is forced to. As a
result, the computer is always considering a set of words that could be the answer. In
order to fool the user into thinking it is playing fairly, the computer only considers words
with the same letter pattern.

For example, suppose that the computer knows the words in the following dictionary: 
ALLY BETA COOL DEAL ELSE FLEW GOOD HOPE IBEX

In a normal game of hangman, the computer would start the game by choosing a word
to guess. In our game, the computer doesn't yet commit to an answer but instead
narrows down its set of possible answers as the user makes guesses. In the log below,
the user’s first guess is 'e'. The computer has to reveal where the letter 'e' appears but
since it hasn't chosen an answer, it has several options. In particular, note that the
dictionary's words fall into 5 families:

 ---- is the pattern for [ally, cool, good]
 e--- is an empty pattern with no possible values.
 -e-- is the pattern for [beta, deal]
 --e- is the pattern for [flew, ibex]
 ---e is the pattern for [hope]
 e--e is the pattern for [else]
 all other patterns are empty.

The computer could choose to reveal any of these 5 patterns. It could use several
different strategies for picking the family to display. For this project, your program will
always choose the largest of the remaining word families. This will leave the
computer's options open and increase its chances of winning. For the example
described above, the computer would pick ----. This reduces the possible answers it
can consider to: ally cool good. Since the computer didn't reveal any letters, it
counts this as a wrong guess and decreases the number of guesses left to 6.

<img width="576" alt="Screenshot 2025-05-10 at 10 39 34 PM" src="https://github.com/user-attachments/assets/9ba406fd-50c0-43e4-92af-5796e7b677a8" />
