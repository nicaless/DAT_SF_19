1) i. Each row is a chipotle order

```bash
head chipotle.csv
```
This shows the columns "order_id", "quantity", "item_name", etc. which led me to this conclusion.

1) ii. There are 1834 Order IDs

```bash
tail order chipotle.csv
```

1) iii. There are 4623 rows

```bash
wc -l chipotle.csv
```

1) iv. There are 368 Steak Burritos and 553 Chicken Burritos.

```bash
grep -o "Steak Burrito" | wc -l
grep -o "Chicken Burrito | wc -l
```

1) v. There are more instances of Chicken Burritos with Black Beans (282) than those with Pinto Beans (105)

```bash 
grep "Chicken Burrito" chipotle.csv | grep -o "Black Beans" | wc -l

grep "Chicken Burrito" chipotle.csv | grep -o "Pinto Beans" | wc -l
```

2) There are 11 .csv and .tsv files.

```bash
ls -R | grep -E '.csv|.tsv' | wc -l
```

3) There are 121 instances of the word "dictionary", case insensitive.

```bash 
grep -r -i "Dictionary" . | wc -w 
```
4) Doing the following

```bash
sort chipotle.tsv | uniq -c | wc -l
```
Yields the number 4564.  That is, there are 4564 unique orders.  However there are 4623 rows of orders.  So in this dataset, there are 4623 - 4564 = 59 orders that have been ordered more than once.  