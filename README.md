#Logan Chaffin March 22/2024
#CSC131-002
#Purpose: Implement a set of functions called ceil, floor, minVal, maxVal, total, mean, median, gcd.
def floor(num):
    """Gets a numeric value, rounds down the number and then returns it"""
    return int(num - (num % 1))
def ceil (num):
    """Round up the number to the next integer value and then returns it but as an integer"""
    if num % 1 == 0:
        return int(num)
    else:
        return int(num + 1)
def minVal (nums):
    """Takes a list of numbers and returns the smallest value in the list"""
    smallest = nums[0]
    for num in nums:
        if num < smallest:
            smallest = num
    return smallest
def maxVal (nums):
    """Takes a list of numbers and returns the largest value in the list"""
    largest = nums[0]
    for num in nums:
        if num > largest:
            largest = num
    return largest
def total(nums):
    """Takes a list of numbers and returns the sum of those value"""
    result = 0
    for num in nums:
        result += num
    return result
def mean(nums):
    """Takes a list of numbers and returns the mean value"""
    total_sum = 0
    count = 0
    for num in nums:
        total_sum += num
        count += 1
    if count == 0:
        return 0
    return total_sum / count
def sort(seq):
    """ Takes a list/tuple of numbers and returns the sorted version (smallest to largest) of the seq."""
    sorted_seq = lst(seq)
    for i in range(len(sorted_seq)):
        for j in range(i + 1, len(sorted_seq)):
            if sorted_seq[j] < sorted_seq[i]:
                sorted_seq[i], sorted_seq[j] = sorted_seq[j], sorted_seq[i]
    return sorted_seq
def median(nums):
""" Takes a list of nubers and returns the median value"""
    sorted_nums = sort(nums)
    length = len(sorted_nums)
    middle = length // 2
    if length % 2 == 0:
        return (sorted_nums[middle - 1] + sorted_nums[middle]) / 2
    else:
        return sorted_nums[middle]
def gcd(a, b):
    """Replicate the Euclid's Algorithm which takes two integers and returns the greatest common denominator of two given integers"""
    if a >= b:
        M = a
        N = b
    else:
        M = b
        N = a

        R = M % N
    while R != 0:
        M = N
        N = R
        R = M % N

    return N

