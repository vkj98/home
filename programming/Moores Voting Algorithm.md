

Leetcode problem at https://leetcode.com/problems/majority-element/description/

Moore's Voting Algorithm, also known as Boyer-Moore Voting Algorithm is used to find a majority element in an array with frequency more than half of the size of the array.

Here is a sample array of numbers in which we have to find the majority element.

2 5 6 6 2 4 5 5 5 5 5

As is obvious here, 5 is the majority element here. Here is the explanation and dry run of the algorithm

We start of by creating 2 variables called majority and count.

To start with, we initialize count to 0 and set majority as the first element.


1. count=0, majority=2
2. Now we iterate over the element, every time we encounter an element which is equal to the majority element, we increment the count. Every time we encounter an element which is not equal to the majority element, we decrement the count. When we are at an element and the count is zero, we set that element as the majority element and increment the count to 1.
3. At the end of the iteration, the number assigned to majority is our majority element.
4. This algorithm works because majority element occurs more than half of the time. So it will be able to counter all the other elements which may have been assigned to majority and triumph at the end.
5. A dry run follows

```

2 5 6 6 2 4 5 5 5 5 5


Step 1 :
count=0, majority=None

Step 2:
Iterating over 2
count=1, majority=2

Step 3:
Iterating over 5
5 is not equal to 2, so we reduce the count
count =0, majority=2

Step 4:
Iterating over 6
count is zero. 
count=1, majority=6

Step 5:
Iterating over 6
count=2, majority=6

Step 6:
Iterating over 2
count=1, majority=6

Step 7:
Iterating over 4
count=0, majority=6

Step 8:
Iterating over 5
Since count is 0, we set majority to 5 and increment the count
count=1, majority=5


Now all the subsequent steps will just increment the count until we reach the end of the array. At the end 5 will be the majority element.

```