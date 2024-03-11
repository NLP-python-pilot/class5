# Assignment #5 - March 4th to March 11th

###### *Solutions for previous assignments can be found here: https://github.com/ponceoscarj/nlp_python_pilot/tree/main*


## Overall Instructions
1. Watch the following video:
    1. Lecture 6: Recursion and Dictionaries. [[Link]](https://ocw.mit.edu/courses/6-0001-introduction-to-computer-science-and-programming-in-python-fall-2016/resources/lecture-6-recursion-and-dictionaries/)
    2. Lecture 7: Testing, Debugging, Exceptions, and Assertions. [[Link]](https://ocw.mit.edu/courses/6-0001-introduction-to-computer-science-and-programming-in-python-fall-2016/resources/lecture-7-testing-debugging-exceptions-and-assertions/)
    3. Lecture 8: Object Oriented Programming. [[Link]](https://ocw.mit.edu/courses/6-0001-introduction-to-computer-science-and-programming-in-python-fall-2016/resources/lecture-8-object-oriented-programming/)


## Python assignment

### Rules:
- Do not use external packages (i.e., regex) **EXCEPT** for the last question

### Submission format:
- Submit your python code to your classroom repository
- Organise your coding by question (e.g., Q1.1.)

### 1. Create a function that converts a list into a dictionary: 
You have to create a function that has two input parameters and returns a dictionary with one key (a string) and one value (a list).

input parameters:
```python
pos = "noun"
items = ["park", "football", "home", "Switzerland"]
```

output (return):
```python
{'noun': ['park', 'football', 'home', 'Switzerland']}
```

Example:
Your function would look like this. You have to replace the underscores with your coding, it can be one line or multiple lines, it's up to you.
```python
def convert_lst_dct(pos, items):
    ______
    ______
    ______
    ______
    return new_dct
```

### 2. Create a function that generates your part-of-speech (POS) grammar:  
Create a function that generates a dictionary (grammar) with multiple keys where each key has a list of strings.

Input parameters:
```python
pos = ["noun", "pronoun", "preposition"]
values_list = [["park", "football", "home", "Switzerland"], 
               ["i", "me", "he", "she"],
               ["to","at"]]
```
output:
```python
grammar = {"noun":["park", "football", "home", "Switzerland"], 
"pronoun":["i", "me", "he", "she"], 
"preposition": ["to","at"]}
```



### 3. Create a function that identifies the part-of-speech (POS) of a sentence - List of lists:  
For this question you will need to use the grammar dictionary (below). The function will input a sentence in the form  of string and it will automatically classify each word's POS based on your grammar and the function will output a list of lists. See below.


Input parameters:
```python
sentence = "I want to play football"
grammar = {"noun":["park", "football", "home", "Switzerland"], "pronoun":["i", "me", "he", "she"],
           "verb":["work", "want", "play", "travel"], 
           "preposition": ["to","at"]}
```

Output:
```python
[['pronoun', 'i'], ['verb', 'want'], ['preposition', 'to'], ['verb', 'play'], ['noun', 'football']]
```

As you see each list has the word and their corresponding POS in the following form `[POS, word]`.

### 4. Create a function that identifies the part-of-speech (POS) of a sentence - Dictionary:  
Same as question 3 but this time your output will be a dictionary where the keys are the words and the values are their corresponding POS. See below.

Input parameters:
```python
sentence = "I want to play football"
grammar = {"noun":["park", "football", "home", "Switzerland"], "pronoun":["i", "me", "he", "she"],
           "verb":["work", "want", "play", "travel"], 
           "preposition": ["to","at"]} 
```

Output:
```python
{'i': 'pronoun', 'want': 'verb', 'to': 'preposition', 'play': 'verb', 'football': 'noun'}
```

As you can see the keys and values are organised in the following form `{POS: word, POS: word, POS:word ...}`

### 5. Create a class that has two main methods and an `__init__` method  
In this question you have to combine what you did on **Question 3** and **Question 4**. 

Your class name will be `pos` without any parent. It has to be initialised with the following two values: 

```python
sentence = "I want to play football"
grammar = {"noun":["park", "football", "home", "Switzerland"], "pronoun":["i", "me", "he", "she"],
           "verb":["work", "want", "play", "travel"], 
           "preposition": ["to","at"]} 
```

Within your class, you will have two methods : `pos_lst` and `pos_dct`. The first (`pos_lst`) will do the same as in your **Question 3** and the second (`pos_dct`) will do the same as in your **Question 4**.

After you create your `pos` class you should be able to run the following code without problems (errors):

```python
pos_class = pos(sentence, grammar)

lst_pos_result = pos_class.pos_lst()
dct_pos_result = pos_class.pos_dct()

print(lst_pos_result)
print(dct_pos_result)
```

### 6. Using assertion and exception
In your `__init__` function introduce two `assert`. One `assert` to make sure that the `sentence` input is a string `str` and  the second `assert` to make sure that the `grammar` input is a dictionary `dict`.

Also, `raise` an error called `ZeroDivisionError` to make sure your sentence has at least one word. I would do this by trying to divide 1 by the length of the sentence. 


### 7. [OPTIONAL] Working with patient-doctor conversations
You are free to use packages. However, bear in mind that it is possible to do this question without importing external packages.

 Create a class that does five things (five different methods):
- Reads the `day1_consultation01.txt` file that has a patient-doctor mock conversation.
- Counts the number of turns made by patients 
- Counts the number of turns made by doctors
- Counts the total number of words spoken by doctors
- Counts the total number of words spoken by patients
