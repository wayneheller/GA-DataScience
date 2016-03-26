## Chipolte Data Exploration Using Command Line

#### Command Line Tasks

> 1 Look at the head and the tail of **chipotle.tsv** in the **data** subdirectory of this repo. Think for a minute about how the data is structured. What do you think each column means? What do you think each row means? Tell me! (If you're unsure, look at more of the file contents.)

    $ less chipotle.tsv to explore the file

|Column Name|Column Definition|
|---|---|
|order_id|Unique order identifier|
|item_name|Description of the item to be prepared and served|
|quantity|The quatity to be prepared and service of this line item|
|choice_description|A list of characteristics describing this line item|
|item_price|The total price of all items and choices on this line (not just unit price).|

The rows represent unique line items on a single order.  An order is comprised of 1 or more line items.

> 2 How many orders do there appear to be?

    $ tail chipotle.tsv 1834** is the last order id in the file.  So assuming that the file is sequential, there are **1834 orders**

> 3 How many lines are in this file?

    $ wc chipotle.tsv** returns 4623 lines.  The first row is the header so I would expect there to be **4622 rows of data**

> 4 Which burrito is more popular, steak or chicken?

    $ grep "Steak Burrito" chipotle.tsv | wc** returns 368 lines

    $ grip "Chicken Burrito" chipotle.tsv | wc** returns 553 lines

Most of the item_uantity values are 1 so we can be reasonable confidently assume that **Chicken is the most popular**

> 5 Do chicken burritos more often have black beans or pinto beans?

    $ grep '\<Chicken Burrito.*Pinto Beans\>' | wc** returns 105 lines

    $ grep '\<Chicken Burrito.*Black Beans\>' | wc** returns 282 lines

**Black Beans** appear to be more popular

> 6 Make a list of all of the CSV or TSV files in the GA-SEA-DAT1 repo (using a single command). You will be working on your local repo on your laptop.  Think about how wildcard characters can help you with this task.

**$ find . -name '*.csv' -o -name '*.tsv'**


> 7 Count the approximate number of occurrences of the word "dictionary" (regardless of case) across all files in the GA-SEA-DAT1 repo.

**$ grep -r - i 'dictionary' .**

> 8 **Optional:** Use the the command line to discover something "interesting" about the Chipotle data. Try using the commands from the "advanced" section!


