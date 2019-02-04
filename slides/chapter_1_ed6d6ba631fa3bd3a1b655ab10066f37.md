---
title: Insert title here
key: ed6d6ba631fa3bd3a1b655ab10066f37

---
## Using the Apriori Algorithm and Analyzing the Data

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
type: "FullCodeSlide"
key: "414ccc4976"
disable_transition: true
```

`@part1`
**First import the libraries.** {{1}}
``` python
from mlxtend.frequent_patterns import association_rules, apriori
```{{1}}

**Second, build a frequent itemset & then define the rules.**{{2}}
``` python
# Use Apriori to build a frequen itemset.
frequent_itemsets = apriori(encoded_data, min_support=0.01, use_colnames=True)

# Define the rules.
rules = association_rules(frequent_itemsets, metric='lift', min_threshold=1.0)
```{{2}}

**Third, examine the data.**{{3}}
``` python
#Show output sorted by confidence
rules.sort_values('confidence', ascending=False)
rules.head(5)   #We can always get more data if we like.
```{{3}}


`@script`
Finally, let's sort the values by the confidence metric and then print out the first five rows using the head method. If we want more rows we can simply pass through a larger number.


---
## Here is the first five rows of our output sorted by lift!

```yaml
type: "TwoRows"
key: "c4abbd588f"
center_content: false
disable_transition: true
```

`@part1`
![](https://assets.datacamp.com/production/repositories/4596/datasets/5ba5f408d6fd1c02e16795e92b20c824d750330f/Annotation%202019-02-03%20072320.jpg)


`@part2`
Here is our new output in a data frame. We now have new columns that give us the different metrics we need to **analyze the data**.


`@script`
We can now see that the data is sent back to us in a new data frame that has our metrics included. From this data frame, we can see the antecedents (the item purchased) and the consequents (the item purchased after the purchase of the antecedents). Two more columns we are concerned with is confidence and lift. Confidence tells us how likely it is that purchasing Item1 (the antecedent) results in a purchase of Item2 (the consequent). Finally, we have lift, the lift refers to how the chances of Item2 being purchased increased given that Item1 is purchased.


---
## Examining the Output

```yaml
type: "FullSlide"
key: "841dad561f"
```

`@part1`
![](https://assets.datacamp.com/production/repositories/4596/datasets/5ba5f408d6fd1c02e16795e92b20c824d750330f/Annotation%202019-02-03%20072320.jpg)
 
- Coffee is commonly bought **after making a purchase for bread or pastries**.

- Pasteries are **commonly bought along with other bread**.

- This can help us optimize product placement, for example **placing freshly made pastries next to our bread**.


`@script`
Now that we have sorted the data. We can clearly see that coffee is very likely to be bought as a consequence of a customer buying bread. What we can tell from this is that coffee is commonly purchased after a purchase of bread has been made. Beyond this we can still examine other relationships. For example, bread is bought with pastries.


---
## Your Turn!

```yaml
type: "FinalSlide"
key: "2153fe9002"
```

`@script`
Now that you've seen my example, it's your turn to recreate my market basket analysis.

