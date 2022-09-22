Indicating the degree of profanity for each sentence
==============================

What Is This?
-------------

This is a simple Python code  intended to provide a degree of profanity of each sentence .

Here is the First Step
----------------------
First step is to make a list of all the words that you would prefer to remain censored for your particular tweet. Below is an example code block of some of the words that we might want to be censored. The users can feel free to add and explore any other type of words as well.

``` racial_slurs= ["idot", "stupid", "black","shit"] ```

For the next step,
-------------------
we will iterate through a file called tweet.txt where the tweets are saved.

``` 
with open ('tweet.txt',"r") as f:
    tweets=f.readlines()
```

Finally, we will define our  custom function that will perform the action of finding racial slurs  in a particular sentence.
```
def degreeOfProfanity(sentence,racial_slurs):
    
    """Finds the DegreeOfProfanity for each sentence

    Parameters
    ----------
    Sentence : List
        The list of splitted words of a tweet
    racial_slurs : List
       A set of racial_slurs 

    Returns
    -------
    Integer
        DegreeofProfanity  of each sentence 
    """

    words=sentence.split(" ") #splitting the words using white space
    print(words)
    total=len(words)
    bad_words=0
    for i in words:
        if i.lower() in racial_slurs: #changing the case of the words to smaller as the tweets are case sensetive
            bad_words+=1
            
    degree=bad_words/total
    
    return degree
```

Finally Lets call the function
------------------------------
```
for tweet in tweets:
    print(degreeOfProfanity(tweet.strip(),racial_slurs))
```
Output
-------
```
['Hi', 'how', 'are', 'you', 'idot']
0.2
['I', 'am', 'fine', 'shit']
0.25
['Idot']
1.0

```
This Function can be more improvised with  NLP. 
