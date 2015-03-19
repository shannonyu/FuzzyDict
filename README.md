# FuzzyDict

Fast Fuzzy String matching dictionary. Based on `Simple and Efficient Algorithm
for Approximate Dictionary Matching` by `Naoaki Okazaki` and `Jun’ichi Tsujii`

## Usage

```scala 

    val fuzzyHash = FuzzyMap(List( ("Barack Obama", "ID1"),
                                   ("Barack O", "ID2"),
                                   ("Barack", "ID3"),
                                    ("Washington", "ID4")))


    fuzzyHash.get("Barack", 1.0, Cosine)
    // Some(List(ID3))

    fuzzyHash.getMatches("Barack", 0.5, Cosine)
    // Some(List((Barack,ID3), (Barack O,ID2), (Barack Obama,ID1)))
```

 - Fuzzy Matches: 
    - Cosine
    - Dice (soon)
    - Jaccard (soon)


## When to Use?
 
 - Finding fuzzy matches against the strings which the map is built on is very fast. So this is useful in scenarios when you have a massive lots of Strings which you want to constantly query using Fuzzy Search



[1] http://www.aclweb.org/anthology/C10-1096

