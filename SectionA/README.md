# Section A


### Overall Feedback

  Nice job on using the dictionary as a frequency counter, its a smart choice since python dictionaries are known to be quite fast. 
  Accessing elements in a dictionary is done in constant time as opposed to linear time in a python list. 
  It also aids the readability of your code and makes it easier to debug.

  However your code currently doesn't run due to incorrect indentation inside of your Solution Class(lines 2 - 10). 
  And on line 5 you omitted passing in an argument into the `sorted` function, this throws a TypeError currently because
  the `sorted` function takes in an iterable(string in our case) as its first argument.
  

### Other Things to note
  * Use more descriptive variable names, this makes it easier for other developers reading your code to understand. 
  * Also consider giving some spacing between blocks of code, this aids readability.
  * It's good practice to document your code by adding comments to key parts of it.
  * For your indentation problems, you could install the Python extension on VSCode, this would help with linting and autoformatting your code.
  * Python naming conventions favours using `snake_case` over `camelCase` for method and variable names


## A better solution may look like this

```python
class Solution:
    # method name in snake_case
    # descriptive name for list of words to be passed as an argument
    def group_anagrams(self, words_list):
        
        # dictionary to store frequency of each sorted word
        result = {}

        # loop through provided list, sort each word and either create a new entry in the dictionary 
        # or append to an already existing one
        # each entry consists of the sorted word as key, and a list of anagrams as value
        for word in words_list:
            # word passed into the sorted function
            sorted_word = "".join(sorted(word))
            if sorted_word in result:
                result[sorted_word].append(word)
            else:
                result[sorted_word] = [word]

          # return all values in dictionary in no particular order
          return list(result.values())

# descriptive solution instance name
solution = Solution()
print(solution.group_anagrams(["eat", "tea", "tan", "ate", "nat", "bat"]))
```
