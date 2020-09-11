# MOOCTextEditor

This is a homework from [Data Structures and Performance](https://www.coursera.org/learn/data-structures-optimizing-performance?specialization=java-object-oriented) by University of California San Diego, which is the part2 of The [Specialization](https://www.coursera.org/specializations/java-object-oriented).

Task is to make a Java application includes six function:
- Load Text
- Compute Flesch Index
- Generate Markov Text
- Edit Random Two Words' Distance
- Spelling Suggestions for Text
- Word AutoComplete
- Spell checking

## Flesch Index

1. [How Easy to Read is Your Writing](https://www.coursera.org/learn/data-structures-optimizing-performance/programming/neATU/how-easy-to-read-is-your-writing)

FleschScore measuring how easy is your writing to read, more information you can click [this](https://yoast.com/flesch-reading-ease-score/) link.
![FleschScore](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/6jRBdXzrEeWcSw5H0E9onQ_da128fae925b2ae11eb087f86707fd8e_Flesch.png?expiry=1599955200000&hmac=jq5_elHbDy8K0hX6kjUCEso0IKvk0YTSX_lDRh8hOeA)

2. Mastering Regular Expression

[Assignment](https://www.coursera.org/learn/data-structures-optimizing-performance/programming/n50OX/spell-checking-and-autocomplete)
## Spell checking  
**class revolved:** all Dictioinary**
Use [TreeSet](https://www.javatpoint.com/java-treeset)(balanced Binary Search Tree) data structure to store all words. It will spend O(logN) to find a word at average. The words put on the Application will be highlighted if mispelled.

## Autocomplete
**class revolved:** AutoCompleteDictionaryTrie, TrieNode

**trie data structure**<br>
tries are trees, but node is hashmap. Providing we build a tree for all English words, maybe 25000, now if we use BST to find a word, the worst case is when the words not in the tree, the complexity is O(log(n)), max search time(最大搜索次数) is 18, but if we use trie, max word length(最大单词长度) is 18, so only when the max length of input word reach 18, there comes the max search time, but at most situation, length of input word(输入单词) is under 10, so the search time will limited under 10, is much better then using BST.

A simple trie node
```
class Trie
  boolean isWord;
  HashMap<Character, TrieNode> children; // a character points to a new TrieNode which string is current string concat this char.
  String text;  //current string
  insert(Character) //
  get();
  ...
```
**AutoCompleteDictionaryTrie：** In this class, we should write methods for implementing a dictionary trie. 
To complement function **Autocomplete**
1. Find the stem
2. Do a level order traversal from there  

<img width="400" height="250" src="https://github.com/ericlan77/MOOCTextEditor/blob/master/images/trie.png"/><br> 

## Spelling Suggestions
<img width="550" height="230" src="https://github.com/ericlan77/MOOCTextEditor/blob/master/images/spellingsuggestion1.png">  
<img width="550" height="230" src="https://github.com/ericlan77/MOOCTextEditor/blob/master/images/spellingsuggestion2.png">  
<img width="550" height="230" src="https://github.com/ericlan77/MOOCTextEditor/blob/master/images/spellingsuggestion3.jpg">

## Word Distance
What path of words takes us from "spell" to "mine"?<br>   
spell -> spill -> pill -> pile -> pine -> mine<br>
Now we know the Edit Distance between them are 5, Edit Distance is the number of modifications you need to make to one string to turn it into another, some applications are Computational Biology and Natural Language Processing.  

<img width="400" height="200" src="https://github.com/ericlan77/MOOCTextEditor/blob/master/images/8CDE966FF9684949A4655685DC31A7A5.jpg"/><br>  

How big the problem space is?<br>  

<img width="450" height="180" src = "https://github.com/ericlan77/MOOCTextEditor/blob/master/images/2distance.jpg">  

So initial complexity of 2 distance away is (52k + 26) ^ 2, which determined by the length of word, we need pruning, remove those are not true words.

