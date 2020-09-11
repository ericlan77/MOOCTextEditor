# MOOCTextEditor

This is a homework from [Data Structures and Performance](https://www.coursera.org/learn/data-structures-optimizing-performance?specialization=java-object-oriented) by University of California San Diego, which is the part2 of The [Specialization](https://www.coursera.org/specializations/java-object-oriented).

Task is to make a simple Java application includes four function:
- Load Text
- Compute Flesch Index
- Generate Markov Text
- Edit Random Two Words' Distance

## Assignment1

1. [How Easy to Read is Your Writing](https://www.coursera.org/learn/data-structures-optimizing-performance/programming/neATU/how-easy-to-read-is-your-writing)

FleschScore measuring how easy is your writing to read, more information you can click [this](https://yoast.com/flesch-reading-ease-score/) link.
![FleschScore](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/6jRBdXzrEeWcSw5H0E9onQ_da128fae925b2ae11eb087f86707fd8e_Flesch.png?expiry=1599955200000&hmac=jq5_elHbDy8K0hX6kjUCEso0IKvk0YTSX_lDRh8hOeA)

2. Mastering Regular Expression
3 ways to combine: Repetition, Concatenation, Alternation

**Repetition**
```
"Hello    helo?"
d.getTokens(" +"); ->["    "]
```
this matches 1 or more spaces.
**Concatenation**
```
"Hello    helo?"
d.getTokens("el"); ->["el","el"]
```
Two regular expressions side by side(el) matches when both appear one after the other.
**Concatenation and Repetition**
```
"Hello    helo?"
d.getTokens("el+"); ->["ell","el"] //+ means one or more

d.getTokens("e(l+)"); // use parens to group r.e.'s if you're not sure of grouping

d.getTokens("el*"); ->["ell","el","e","el","e"] // * means zero or more
``` 
**Alternation**
```
d.getTokens("el|lo"); -> ["el","lo","el","lo"] // | means or
```
**Character classes**
```
d.getTokens()
```
To Be Continue...
