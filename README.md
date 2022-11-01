# Python---Word-Counter
Created using PyCharm IDE on 1st November 2022.

Project: Create a word frequency tracker from a sentence, which ignores appended special characters on each word, with the exception of spacebar.

Test sentence: The fat cat beat the fat cat.

This project is divided into 4 phases:
1. Project initial function is to calculate number of words in a sentence. raw_input() was initially used but is then replaced with input() because there was a problem with it.

2. Code is then expanded to have word frequency function. This leads to the 3rd phase because the real output does not match the expected output.

  Real output:
  {'The': 1, 'the': 1, 'fat': 2, 'cat': 1, 'beat': 1, 'cat.': 1}

  Expected output:
  {'the': 2, 'fat': 2, 'cat': 2, 'beat': 1}

3. This phase is to create a simple function that omits any unwanted special characters, without removing the spaces between each words, so to not make all 7 words into 1 big word.
List of special characters: ! # $ % & @ [ ] . , _ ? ( ) { } = 

4. The last phase is to find the correct function for 3rd phase. 
The first function used which did not work as expected is: 

  special_characters = ['!', '#', '$', '%', '&', '@', '[', ']', '.', '_', '?', '(', ')', '{', '}', '=', ',']
  for i in special_characters:
      converted_sentence = lower_sentence.replace(i,'')
    
The second function used which still did not work is:

  import re
  .
  .
  converted_sentence = re.sub('[^A-Za-z0-9]+', '', lower_sentence)

The suitable function is by using join + generator function:

  special_characters = ['!', '#', '$', '%', '&', '@', '[', ']', '.', '_', '?', '(', ')', '{', '}', '=', ',']
  converted_sentence = ''.join(filter(lambda i:i not in special_characters, lower_sentence))

Below is the full output after code completion:

  Welcome to the word frequency tracker. All you need to do is input a sentence.
  Please enter a sentence: The fat cat beat the fat cat.

  The sentence contains a total of 7 words.

  New sentence without special characters:  the fat cat beat the fat cat

  The following is the word frequency: 
  {'the': 2, 'fat': 2, 'cat': 2, 'beat': 1}
