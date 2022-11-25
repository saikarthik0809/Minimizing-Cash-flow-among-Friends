Here there are N no.of people who have borrowed money from each other. Instead
of exchanging money many times we’ll be using a greedy approach to make the
number of transactions as low as possible.

Problem Description:

Once the net amount for every person is evaluated, find two persons with
maximum and minimum net amounts. These two persons are the most
creditors and debtors. The person with a minimum of two is our first person to
be settled and removed from the list. Let the minimum of two amounts be x.
We pay ‘x’ amount from the maximum debtor to maximum creditor and settle
one person. If x is equal to the maximum debit, then maximum debtor is
settled, else maximum creditor is settled.

GREEDY APPROACH:

The approach we will be using for minimizing cash flow is the Greedy Algorithm. The greedy
approach is used to build the solution in pieces, and this is what we want to minimize the
cash flow. At every step, we will settle all the amounts of one person and recur for the
remaining n-1 persons.
Calculate the net amount for every person, which can be calculated by subtracting all the
debts, i.e., the amount to be paid from all credit, i.e., the amount to be paid to him. After this,
we will find two persons with the maximum and the minimum net amounts. The person with
a minimum of two is our first person to be settled and removed from the list.
Following algorithm will be done for every person varying 'i' from 0 to n-1.
1. The first step will be to calculate the net amount for every person and store it in
an amount array.
1. Net amount = sum(received money) - sum(sent money).
2. Find the two people that have the most credit and the most debt. Let the maximum
amount to be credited from the maximum creditor be max_credit and the maximum
amount to be debited from the maximum debtor be max_debit. Let the maximum
debtor be debt and maximum creditor be cred.
3. Let the minimum of two amounts be 'y'.
4. If y equals max_credit, delete cred from the list and repeat for the remaining (n-1)
people.
5. If y equals max_debit, delete debt from the group of people and repeat for
recursion.
6. If the amount is 0, then the settlement is done.
Algorithm:
● Create a net amount array ‘net amount’
● Fill this array, Now for every friend ‘i’
○ ‘netAmount[i]’= sum of all received money by ‘i-th’ friend - the sum of all sent money by
‘i-th’ friend.
● Create a 2-D matrix to store the ‘answer’.
● Iterate a while loop until all the values of ‘net amount’ is not ‘0’
○ Find the minimum and maximum of ‘net amount’
○ Suppose ‘x’ index value is the max net amount and ‘y’ index is min net
amount, then:
■ ‘netAmount[x] = netAmount[x]- abs( netAmount[y] )’
■ Update ‘answer[y][x] = abs( netAmount[y] )
■ It represents that the ‘y-th’ friend will pay ‘netAmount[y]’ to ‘x-th’
friend.
■ Set ‘netAmount[y] = 0’.
● In the end, return ‘answer’.
