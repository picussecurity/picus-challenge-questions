Pascal's Triangle is an arithmetical triangle you can use for some neat things in mathematics. Here's how you construct it:
```                 
                             1
                           1   1
                         1   2   1
                       1   3   3   1
                     1   4   6   4   1
                   1   5  10   10  5   1
                 1   6  15  20   15  6   1
               1   7  21  35   35  21  7   1
                             .
                             .
                             .
````                      
You start out with the top two rows: 1, and 1 1. Then to construct each entry in the next row, you look at the two entries above it (i.e. the one above it and to the right, and the one above it and to the left). At the beginning and the end of each row, when there's only one number above, put a 1. You might even think of this rule (for placing the 1's) as included in the first rule: for instance, to get the first 1 in any line, you add up the number above and to the left (since there is no number there, pretend it's zero) and the number above and to the right (1), and get a sum of 1.
  
Write a go file that produce Pascal's triangle with the given depth.
  
  
##### Example Output:

````
 
   1 
   1     1 
   1     2     1 
   1     3     3     1 
   1     4     6     4     1 
   1     5    10    10     5     1 
   1     6    15    20    15     6     1 
   1     7    21    35    35    21     7     1 
   1     8    28    56    70    56    28     8     1 
   1     9    36    84   126   126    84    36     9     1 
````

