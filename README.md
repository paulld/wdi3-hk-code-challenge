# Code Challenge
Complete the following problems using Coffescript in the order of your choice. Work alone or in groups using any resources available to you (but don't look up code solutions!).
There are example parameters and expected results provided for each challenge. The points associated with each problem are in parenthesis following the prompt.

## Challenge: Simple Add 
Using Coffeescript, add up all the numbers from 1 to num, where num is a number.
##### (5 points)
##### Example: num = 30
##### Expected result: 465

	simpleAdd = (num) ->
  		total = 0
  		for i in [1..num]
    		total = total + i
  		total
  		
	console.log simpleAdd(30)
  
## Challenge: Palindrome 
Using Coffeescript, write a function to return the string "true" if str, where str is a string, is a palindrome.
#####(10 points)
##### Example 1: str = "racecar"
##### Expected result: "true"
##### Example 2: str = "chipmunk"
##### Expected result: "false"

	palindrome = (string) ->
  		if string.toLowerCase().split("") is string.toLowerCase.split("").reverse
    		"true"
  		else
    		"false"

	console.log palindrome("racecar")
	console.log palindrome("chipmunk")

## Challenge: Second Best and Worst
Using Coffeescript, take the array of numbers stored in arr, where arr is an array, and return the second lowest and second greatest numbers, respectively, separated by a space. 
##### (10 points)
##### Example: arr = [17, 7, 12, 98, 106]
##### Expected result: 12 98

	seconds = (arr) ->
  		numSort = (a,b) ->
    		a - b
  		sortedArray = arr.sort(numSort)
  		secondWorst = sortedArray[1]
  		secondBest = sortedArray[sortedArray.length - 2]
  		secondWorst, secondBest


	console.log array = [17, 7, 12, 98, 106]
	seconds(array)

## Challenge: Find the Numbers
Using Coffeescript, take str, where str is a string, and search for all the numbers in the string, add them together, then return that final number divided by the total amount of letters in the string (rounded to the nearest whole number). Only single digit numbers separated by spaces will be used throughout the whole string (So this won't ever be the case: hello44444 world). Each string will also have at least one letter.
#####(15 points)
##### Example: str = "Hello6 9World 2, Nic8e D7ay!"
##### Expected Result: 2

	numberSearch = (str) ->

  		nums = str.match(/\d+/g).map (num) -> parseInt(num)
  		sum = nums.reduce (p, c, i, a) -> p + c

  		chars = str.match(/[a-zA-Z]/g)
  		num_chars = chars.length

  		Math.round sum / num_chars

	str = "Hello6 9World 2, Nic8e D7ay!"
	console.log "Str: " + "Hello6 9World 2, Nic8e D7ay!"
	console.log "Answer: " + numberSearch(str)

## Challenge: Half Christmas Tree in Summer Humidity
Using Coffeescript, write a summerTree function that creates a tree with the number of levels in the tree equal to int, where in is an integer. 
#####(15 points)
##### Example: int = 5
##### Expected Result:
####*
####**
####***
####****
####*****

	summerTree = (levels) ->
  		for level in [1..levels]
    		stars = ''
    		for n in [1..level]
      			stars = stars + '*'
    		console.log stars

	summerTree(5)

## Challenge: Bubble Sort
Using Coffeescript,write a bubbleSort function to sort arr, where arr is an array of integers. (Bubblesort: http://en.wikipedia.org/wiki/Bubble_sort) 
#####(25 points)
##### Example: arr = [98, 734, 7, 3, 5, 29, 10, 87, 33, 54, 72, 461]
##### Expected Result: [3, 5, 7, 10, 29, 33, 54, 72, 87, 98, 461, 734]


## Challenge: Fibonacci
Using Coffeescript, write a fibonacci function, either recursive or iterative, that takes int, where int is an integer, representing the index of a number in the fibonacci sequence and outputs the fibonacci number of that index. (Fibonacci Sequence: http://en.wikipedia.org/wiki/Fibonacci_number)
##### (25 points)
##### Bonus: Implement both recursive and iterative solutions. (Total = 75 points)
##### Example: int = 10
##### Expected Result: 55

	fib_recursive = (n) ->
  		if n == 0 || n == 1 then return n
  		else fib_recursive(n-1) + fib_recursive(n-2)

	console.log fib_recursive(10)



