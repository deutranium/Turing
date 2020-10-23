---
layout: post
title:  "Divide and Conquer Algorithms"
author: abhi
categories: [ Divide and Conquer ]
image: assets/images/divide_and_conquer.jpg
---

## What is "Divide and Conquer"?

Divide and Conquer algorithms are a class of algorithms that function based off of a “divide and conquer” concept. The concept of divide and conquer is a colonization strategy commonly used by the British during their extensive colonization. In this strategy, the population of a colony would be segregated by cultural, racial, or ideological differences to create a divide in society which led to the nation/colony falling apart making it easier for the colonizers to control the people of the land.

Certain algorithms make use of a part of this strategy to easier solve certain problems. These algorithms work by dividing the main problem into a set of sub-problems, which are again divided into a set of sub-problems, and so on until a problem becomes small/simple enough to be solved easily. Then the solutions to these many sub-problems are combined to find the solution to the main problem.

## How Divide and Conquer algorithms work:
Divide and Conquer algorithms have 3 main steps:
* Divide: Divide the problem into similar sub-problems
* Conquer: Recursively solving these sub-problems (using the same divide and conquer strategy)
* Combine: Combine the results of the sub-problems to get the solution to the main problem.

Some popular Divide and Conquer algorithms are:
* MergeSort: MergeSort is a popular sorting algorithm that sorts an array of ‘n’ numbers with a complexity of O(n*log(n)). More information on the MergeSort algorithm can be found here.
* QuickSort: QuickSort, like MergeSort, is a sorting algorithm that also relies on the divide and conquer strategy but does so in a different way. QuickSort has the same complexity as MergeSort but if implemented efficiently can be 2-3 times as fast as MergeSort. More information on the QuickSort algorithm can be found here.
* Binary Search: Binary Search is a searching algorithm the allows to find a number in a sorted array of numbers. It relies on the divide and conquer algorithm to repeatedly cut down the size of the array that if is searching until it finds the element it’s looking for. Using this algorithm, we can search a sorted array with a time complexity of O(logn).
* Quick Exponentiation: Quick exponentiation is a method of calculating exponents that utilizes the divide and conquer algorithm. Using this method, we can find the value of XY with a time complexity of O(logn).

## A general example:
Lets assume a problem which we will represent by S(0,1). Where S(0,1) represents that this problem covers the entirety of the problem and S(x,y) would represent the sub-problem that covers a portion of the main problem from x->y. 

For such a problem, if a divide and conquer approach were suitable, we would begin to recursively break down the problem into smaller subparts. i.e. We would proceed by saying that S(0,1) = S(0,0.5) + S(0.5,1) , where ‘+’ represents the suitable combination of the solutions to the sub-problems. From here we would the recursively break down the problem to make it easier and easier to solve it.

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
