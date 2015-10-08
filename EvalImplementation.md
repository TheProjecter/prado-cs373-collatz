My solution of eval is similar in both python and java. My Java implementation uses a Hashtable<Integer,Integer> and my python implementation  uses a dictionary where the keys and values are both ints, so they essentially work the same way.

Since the base case occurs when we reach 1 and the cycle length of 1 is 1, the first entry on the containers is (1:1). The "max"(java) and "maxx"(py) variables are initialized to 1, since this is the lowest possible cycle length.

An outer for loop serves to go through the range given to eval. For each iteration of the for loop, a counter will be set to 0, and variable "current" will be set initially to "range" (r in python) and will change each iteration of the while loop until a match is found in the cache.

For each iteration of the while loop we will increase a counter that keeps track of our cycle length, until we run into a value that we already know from the cache. Depending on whether current is odd or even, it is updated accordingly each iteration. Since the cache initially holds (1:1), in the event that "current" is reduced down to 1, the while loop will still terminate.

After the while loop terminates, we add the cycle length of the known number to the current count to get the total cycle length for whatever number in the range we are in. The cycle length for said number is then stored in the containers for other iterations to use. We then determine if the new cycle length is longer than the existing max, and update it if needed.

Once the for loop terminates, eval returns the max cycle length for the given range.