---
title: Insert title here
key: ed6d6ba631fa3bd3a1b655ab10066f37

---
## Implementing a Market Basket Analysis

```yaml
type: "TitleSlide"
key: "ca2c3c41c6"
```

`@lower_third`

name: Alex Reed
title: Senior Data Science Analyst


`@script`
Now that we've encoded our data we can begin to perform our our market basket analysis. This will be broken into two parts building our frequent item set & then defining the association rules to filter the results.


---
## Using the Apriroi Algorithm

```yaml
type: "TwoColumns"
key: "8341baec8a"
```

`@part1`
**#Generates rules from the itemsets by defining a minimum threshold.
rules = association_rules(encoded_data, min_support=0.1, use_colnames=False)**

```
#Generates rules from the itemsets by defining a minimum threshold.
rules = association_rules(encoded_data, min_support=0.1, use_colnames=False)
```


`@part2`



`@script`
The first thing we will need to do is call the import the Aprior function from the MlExtend library. After that, we will pass through the encoded data frame from our previous module into the Apriror function. Next, we will define two parameters, the min_support & use_colnames. The use_colnames will use the column names we passed through in our data frame. The min_support defines our support metric threshold, the lower it is the more results we will see & vice versa it ranges between 0 & 1. We will set it equal to .01 so we get an optimal amount of transactions. Finally let's print out the first five rows using the head method.


---
## Using the Apriroi Algorithm

```yaml
type: "FullCodeSlide"
key: "54738b5816"
```

`@part1`
**First import the libraries.
**
```
from mlxtend.frequent_patterns import association_rules, apriori
```

**Second, build a frequent itemset & then define the rules.**
```
# Use Apriori to build a frequen itemset.
frequent_itemsets = apriori(encoded_data, min_support=0.01, use_colnames=True)

# Define the rules.
rules = association_rules(frequent_itemsets, metric='lift', min_threshold=1.0)
```

**Third, examine the data.**
```
#Show output sorted by lift
rules.sort_values('lift', ascending=False)
rules.head(5)
```


`@script`
The first thing we will need to do is call the import the Aprior function from the MlExtend library. After that, we will pass through the encoded data frame from our previous module into the Apriror function. Next, we will define two parameters, the min_support & use_colnames. The use_colnames will use the column names we passed through in our data frame. The min_support defines our support metric threshold, the lower it is the more results we will see & vice versa it ranges between 0 & 1. We will set it equal to .01 so we get an optimal amount of transactions. Finally let's print out the first five rows using the head method.


---
## Here is the output...

```yaml
type: "FullImageSlide"
key: "9f79bdfddb"
```

`@part1`



`@script`



---
## Final Slide

```yaml
type: "FinalSlide"
key: "2153fe9002"
```

`@script`


