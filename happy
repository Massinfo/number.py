#! /usr/bin/env python3
# coding=utf-8

# Check if a number is happy or sad
# http://en.wikipedia.org/wiki/Happy_number

def happy(number, past = None):
	def happy_calc(number):
		return sum((int(digit)**2 for digit in str(number)))

	# Default arguments are mutable and evaluated _once_
	# when the function is defined, if a mutable default argument
	# is used (like past=set()), you _will_ have mutated 
	# that object for future calls.
	if past == None:
		past = set()

	number = happy_calc(number)
	if number == 1:
		return True
	if number in past:
		return False
	past.add(number)
	return happy(number, past)


if __name__ == '__main__':
	happy_numbers = [1, 7, 10, 13, 19, 23, 28, 31, 998, 1000]
	assert all((happy(i) for i in happy_numbers))
	sad_numbers = [0, 2, 3, 4, 5, 6, 8, 9, 11, 12, 997, 999]
	assert all((not happy(i) for i in sad_numbers))
	assert len([i for i in range(1,1001) if happy(i)]) == 143
