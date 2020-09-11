# MOOCTextEditor

This is a homework from [Data Structures and Performance](https://www.coursera.org/learn/data-structures-optimizing-performance?specialization=java-object-oriented) by University of California San Diego, which is the part2 of The [Specialization](https://www.coursera.org/specializations/java-object-oriented).

Task is to make a Java application includes six function:
- Load Text
- Compute Flesch Index
- Generate Markov Text
- Edit Random Two Words' Distance
- Spelling Suggestions for Text
- Word AutoComplete

## Assignment

1. [How Easy to Read is Your Writing](https://www.coursera.org/learn/data-structures-optimizing-performance/programming/neATU/how-easy-to-read-is-your-writing)

FleschScore measuring how easy is your writing to read, more information you can click [this](https://yoast.com/flesch-reading-ease-score/) link.
![FleschScore](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/6jRBdXzrEeWcSw5H0E9onQ_da128fae925b2ae11eb087f86707fd8e_Flesch.png?expiry=1599955200000&hmac=jq5_elHbDy8K0hX6kjUCEso0IKvk0YTSX_lDRh8hOeA)

2. Mastering Regular Expression

## Assignment2
**trie data structure**<br>
tries are trees, but node is hashmap. Providing we build a tree for all English words, maybe 25000, now if we use BST to find a word, the worst case is when the words not in the tree, the complexity is O(log(n)), max search time(最大搜索次数) is 18, but if we use trie, max word length(最大单词长度) is 18, so only when the max length of input word reach 18, there comes the max search time, but at most situation, length of input word(输入单词) is under 10, so the search time will limited under 10, is much better then using BST.

A simple trie node
```
class Trie
  boolean isWord;
  HashMap<Character, TrieNode> children;
  String text;
  public void put(key, value);
  public Trie get(key);
```

To complement function **Autocomplete**
1. Find the stem
2. Do a level order traversal from there

To Be Continue...
