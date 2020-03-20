#### Please add your answers to the ***Analysis of  Algorithms*** exercises here.

## Exercise I

a) O(n^3) / O(n^2) -> ANSWER: O(n)

 a = 0
    while (a < n * n * n): # O(n^3)
      a = a + n * n        # O(n^2)

b)O(n) * log m -> ANSWER: O(n log(m))

sum = 0
    for i in range(n): O(n)
      j = 1
      while j < n: 
        j *= 2 O(log m)
        sum += 1

c) ANSWER: O(n)

def bunnyEars(bunnies):
      if bunnies == 0:
        return 0

      return 2 + bunnyEars(bunnies-1) O(n)

## Exercise II

Requirements:
    n-story building
    egg is broken if thrown off floor f or higher
    determine f such that number of dropped/broken eggs is minimized -> best O(n)

    fastest way to find f is using binary search

Algorithm:
    go to floor n//2, the middle story of the building
        drop the egg, if it breaks:
            go to floor middle - (n - middle) // 2 story of the building and drop again
        else if the egg doesn't break:
            go to the floor (n -middle) // 2  + middle story of the building and drop again
    repeat with recalculated values for n and middle until there are no floors left, the last floor the egg was dropped and survived is f

    when you shift floors, the floors in the direction you didn't go in are excluded. Thus you have a
        new subbuilding and the top floor n and middle have to be recalculated. Once you have the new values you can
        use the above algorithm to continue checking out floors until you're not left with any other floors. The last floor
        that the egg didn't break is the value of f 

The run time complexity of this solution is O(log n)