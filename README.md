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
  		if string.toLowerCase() is string.toLowerCase().split('').reverse().join('')
	    		console.log "\"#{string}\" is a palindrome!"
  		else
	    		console.log "\"#{string}\" is a NOT palindrome"

	palindrome("Racecar")
	palindrome("chipmunk")

## Challenge: Second Best and Worst
Using Coffeescript, take the array of numbers stored in arr, where arr is an array, and return the second lowest and second greatest numbers, respectively, separated by a space. 
##### (10 points)
##### Example: arr = [17, 7, 12, 98, 106]
##### Expected result: 12 98

	seconds = (arr) ->
		numSort = (a,b) ->
			a - b
		total = arr.length
		secondLow = (array) ->
	    		array = array.sort(numSort)
	    		for i in [0..total]
				if array[i] > array[0]
					return array[i]
		secondHigh = (array) ->
			array = array.sort(numSort).reverse()
			for i in [0..total]
				if array[i] < array[0]
					return array[i]
		console.log "The second lowest is #{secondLow arr}
		and the second highest is #{secondHigh arr}"
	
	seconds [1,10,2,1,10,8,11,100,102,102]


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
  		stars = ''
  		for level in [1..levels]
      			stars += '*'
    			console.log stars

	summerTree(5)

## Challenge: Bubble Sort
Using Coffeescript,write a bubbleSort function to sort arr, where arr is an array of integers. (Bubblesort: http://en.wikipedia.org/wiki/Bubble_sort) 
#####(25 points)
##### Example: arr = [98, 734, 7, 3, 5, 29, 10, 87, 33, 54, 72, 461]
##### Expected Result: [3, 5, 7, 10, 29, 33, 54, 72, 87, 98, 461, 734]

	bubbleSort = (arr) ->
		for y in [0..arr.length-2]
			y =+ 1
			for i in [0..arr.length-2]
				if arr[i] > arr[i+1]
					temp = arr[i+1]
					arr[i+1] = arr[i]
					arr[i] = temp
		console.log arr

bubbleSort [98, 734, 7, 3, 5, 29, 10, 87, 33, 54, 72, 461]
bubbleSort [99, 99, 99, 99, 99, 98, 97, 96, 95, 94, 93, 92, 91, 90, 89, 88, 87, 86, 85]


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



