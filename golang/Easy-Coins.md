#### Write a program:

##### Programming Challenge Description:
The goal of this challenge is to design a cash register program.
You will be given two decimal numbers. The first is the purchase price (PP) of the item.
The second is the cash (CH) given by the customer.
Your register currently has the following bills/coins within it:
````
'PENNY': .01,
'NICKEL': .05,
'DIME': .10,
'QUARTER': .25,
'HALF DOLLAR': .50,
'ONE': 1.00,
'TWO': 2.00,
'FIVE': 5.00,
'TEN': 10.00,
'TWENTY': 20.00,
'FIFTY': 50.00,
'ONE HUNDRED': 100.00
````

The aim of the program is to calculate the change that has to be returned to the customer.

#### Input:
Your program should read lines of text from standard input.
Each line contains two numbers which are separated by a semicolon.
The first is the Purchase price (PP) and the second is the cash(CH) given by the customer.

#### Output:
For each line of input print a single line to standard output which is the change to be returned to the customer.
In case the CH < PP, print out ERROR. If CH == PP, print out ZERO.
For all other cases print the amount that needs to be returned, in terms of the currency values provided.
The output should be alphabetically sorted.

````
Test 1
Test Input : 15.94;16.00
Expected Output : NICKEL,PENNY


Test 2
Test Input : Input17;16
Expected Output : ERROR  

Test 3
Test Input : 35;35
Expected Output : ZERO  


Test 4
Test Input : 45;50
Expected Output : FIVE
````