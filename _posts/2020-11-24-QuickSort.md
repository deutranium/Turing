---
layout: post
title:  "QuickSort"
author: abhi
categories: [ Divide and Conquer, QuickSortSort ]
image: assets/images/QuickSort.jpg
---

Ever wanted to know what QuickSort is? Or even just wondered how the person who made could be so confident in is algorithm that he called it "quick"? Well let's find out in this article.

QuickSort is a divide and conquer based sorting algorithm made by Tony Hoare in 1959. It's one of the most frequently used sorting algorithms today.

Before you read this article, you should check out our article on [MergeSort]({{ site.baseurl }}{% post_url 2020-11-16-MergeSort %} as it will make this article easier to understand.

## How does QuickSort work?

An easy way to think about how QuickSort works would be to sort an array with respect to an element, but what does it mean to sort an array with respect to an element? In this sense of the phrase it is to ensure that every element to the left of it (the chosen element) is less than it, and every element to the right of it is greater than it. So essentially, when viewing the array from the perspective of the chosen element, it should be sorted.

In slightly more technical terms, the main idea of QuickSort is to pick an element (called a "pivot") and rearrange the given list of elements such that all elements to the left of the pivot are less than the pivot and all elements to the right of it are greater than it (Note: here greater than and less than are used as an example. Similar to MergeSort, any comparator can be used to compare and re-order the elements).

Just as in MergeSort, we still do split the array into subparts based on the pivot element and sort them separately. The main difference between the two is how they split the array.

Now we need to pick this pivot element and there are many ways to do so, based on which there will be slight changes in the implementation of the algorithm. The most commonly used ways of picking the pivot are:

- Always pick the first element
- Always pick the last element
- Pick a random element
- Pick the median

Each of these ways will have their own quirks and exceptions so we unfortunately won't go through them. Instead we'll go over how a generic implementation of QuickSort.

## Pseudocode

``` c++
quickSort (int * arr, int start, int end)
{
    if(start<end)	// We only sort the array if there is more than one element.
    {
        int pi = partition(arr,start,end);	//This function gives us the partitioning index and is the main variation betwwen different implementations of QuickSort
        
        quickSort(arr,start,pi-1);
        quicksort(arr,pi+1,end);
    }
}
```

The above pseudocode is common to all implementations of QuickSort. The variation lies in how you select the pivot and how you rearrange the array accordingly.

Now let's talk about rearranging the array once you've selected your pivot. All that you have to do is ensure that every element that is less than your pivot, comes before your pivot. Simple enough right? Here's an example of how to do it (taking the last element as pivot).

``` c++
partition (int * arr, int start, int end)
{
    int pivot = arr[end];  
    i = (start - 1)
        
    for (j = start; j < end; j++)
    {
        // Here we iterate over all the elements and move any element less than the pivot to the start of the array.
        if (arr[j] < pivot)
        {
            i++;
            swap(arr[i], arr[j]);
        }
    }
    swap(arr[i + 1], arr[end])	//Move the pivot element to it's appropriate location
    return (i + 1)
}
```