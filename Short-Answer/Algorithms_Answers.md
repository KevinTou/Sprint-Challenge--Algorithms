#### Please add your answers to the **_Analysis of Algorithms_** exercises here.

## Exercise I

a) O(2nk), for a given n, the loop runs n times. Given n, the amount of moves doubles. With this trend, the complexity is considered linear.
It could be said that it will roughly be `O(n)`.

```python
    a = 0 # O(1)
    while (a < n * n * n): # O(nk) + # O(nk)
      a = a + n * n
```

b) O(n \* n \* nk), for a given n. The for loop is dependent on n, the while loop is dependent on n, and multiplication is nk. Since the while loop is nest within the for loop,
you multiply the complexities, which give roughly `O(kn^3)`, where k is a constant.

```python
    sum = 0 # O(1)
    for i in range(n): # O(n)
      j = 1 # O(1)
      while j < n: # O(n)
        j *= 2 # O(nk)
        sum += 1 # O(1)
```

c) `O(n)`, for a given n, the loop runs n times. It is similar to a for loop and will iterate until n == 0.

```python
    def bunnyEars(bunnies):
      if bunnies == 0:
        return 0 # O(1)

      return 2 + bunnyEars(bunnies-1) # O(n)
```

## Exercise II

`f` = number of floor
`n` = n-story of the building

```python
'''
  1. Find the middle floor of the building and drop an egg from it.
  2. If the egg breaks, you can eliminate the top half of the floors since the egg will break from anywhere past that point.
  3. If the egg doesn't break, you can eliminate the bottom half of the floors since the egg won't break past that point.
  4. Find the middle floor from the remaining floors and repeat until you reach the minimum n-story.
'''
```

You're essentially implementing a binary search, which has a run-time complexity of O(log n).
