---
layout: post
title:  "Divide and Conquer Algorithms"
author: abhi
categories: [ Divide and Conquer ]
image: assets/images/divide_and_conquer.jpg
---

## What is "Divide and Conquer"?

Divide and Conquer is a class of algorithms based on the “Divide and Conquer” concept,  a colonization strategy commonly used by the British during their extensive colonization. In this strategy, the population of a colony would be segregated by cultural, racial, or ideological differences to create a divide in society, which led to the nation/colony falling apart.

Similarly, Divide and Conquer algorithms work by dividing the main problem into a set of sub-problems, which are further divided into a set of sub-problems, and so on until the sub-problem becomes small/simple enough to be solved easily. Then the solutions to these sub-problems are combined to find the solution to the main problem.

## How Divide and Conquer algorithms work:
Divide and Conquer algorithms have three main steps:
1. Divide: Divide the problem into similar sub-problems
2. Conquer: Recursively solving these sub-problems (using the same divide and conquer strategy)
3. Combine: Combine the results of the sub-problems to get the solution to the main problem.

Some prevalent Divide and Conquer algorithms are:
* MergeSort: MergeSort is a popular sorting algorithm that sorts an array of ‘n’ numbers by splitting it into multiple smaller sorted arrays and then merging them to create a larger sorted array. This way, it can sort an array of numbers with a time complexity of O(n*log(n)).
* QuickSort: QuickSort, like MergeSort, is a sorting algorithm that also relies on the divide and conquer strategy but does so in a different way. QuickSort has the same complexity as MergeSort, but it can run 2-3 times as fast as MergeSort in a practical application if implemented cleverly.
* Binary Search: Binary Search is a searching algorithm the allows us to find a specific number in a sorted array of numbers. It relies on the divide and conquer algorithm to repeatedly cut down the size of the array being searched until it finds the element. Using this algorithm, we can search a sorted array with a time complexity of O(log(n)).
* Quick Exponentiation: Quick exponentiation is a method that utilizes the divide and conquer algorithm to calculate the value of exponents. Using this method, we can find the value of X<sup>Y</sup> with a time complexity of O(logn).

## A general example:
Let’s define a problem as S(x,y) working on the portion (x,y), a subset of (0,1). Here, the complete problem will be represented by S(0,1), and S(x,y) would represent a sub-problem.

For such a problem, if a divide and conquer approach were suitable, we would begin to recursively break down the problem into smaller subparts, i.e., we would proceed by saying that S(0,1) = S(0,mid1) + S(mid1,mid2) … + S(midN,1), where ‘+’ represents the suitable combination of the solutions to the sub-problems. We would then recursively break down the sub-problems to make it easier to solve.


## Psuedocode:
```
solve (int a, int b)
{
	If(base case condition)
    	{
		//solve the base case and return the answer
	}
	Else
    	{
		mid=(a+b)/2
		A=solve(a,mid)
		B=solve(mid,b)
		Return combine(A,B)
    	}
}
```
