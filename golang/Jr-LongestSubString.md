### Find the longest sub string of a word after concatenation of given words array

An Array of N words is given.Each word consists of small letter('a'-'z') .Our goal is to concatenate the words in such a way as to obtain a single word with longest possible substring composed of one particular letter.Find the length of such substring.

````
Ex. 1)N=3 words=["aaba","aaaa","bbab"] maxSubstring=6 of letter a
````
concatenated word=words[1]+word[0]+word[2]="aaaaaababbab"
````
2)N=3 words=["xxbxx","xbx","x"] maxSubstring=4 of letter x
````
concatenated word=words[0]+word[2]+word[1]="xxbxxxxbx"

Brute Force Code Till Now:

Find all combination of string and calculate the max sub-string Complexity O(2^n) Need a better logic to reduce time complexity