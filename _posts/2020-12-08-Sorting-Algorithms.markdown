---
layout: single
title:  "Overview of Various Sorting Algorithms"
date:   2020-12-08 14:00:23 +0100
categories: compsci
tags: code
excerpt: Soriting algorithms overview
---

# Bubble Sort

## Description

 * Loops through an array.
 * Compares neighboring elements.
 * If sorting needs to be in ascending order then smallest values bubbled towards the start of the array
 * Each pass starts at position 0 and ensures that one value is exactly where it is supposed to be.

 Bubble sort has `n` elements and thus `n-1` passes.


## Pseudocode

{% highlight python linenos %}

ARR =  [64, 34, 25, 12, 22, 11, 90]  #TO BE SORTED IN ASCENDING ORDER
N = LEN(ARR)						 #NUMBER OF ELEMENTS IN THE ARRAY

FOR I IN RANGE (N-1)      # LOOP FROM 0 TO N-1
     #LOOP FROM 0 TO N-I-1 (SINCE VALUES ALREADY SORTED). LESSER VALUES EACH TIME.
      FOR J IN RANGE(0, N-I-1)   
           IF(ARR[J] > ARR[J+1])    #IF VALUE GREATER THAN NEXT NEIGHBOR
              TEMP = ARR[J]           #SWAP THE VALUES
              ARR[J] = ARR[J+1]
              ARR[J+1] = TEMP

PRINT(ARR)           

{% endhighlight %}


## Java

{% highlight java linenos %}

void bubbleSort(int arr[]) 
    { 
        int n = arr.length; 
        for (int i = 0; i < n-1; i++) 
            for (int j = 0; j < n-i-1; j++) 
                if (arr[j] > arr[j+1]) 
                { 
                    // swap arr[j+1] and arr[j] 
                    int temp = arr[j]; 
                    arr[j] = arr[j+1]; 
                    arr[j+1] = temp; 
                } 
    }        

{% endhighlight %}

 

# Selection Sort

## Description

Unlike Bubble Sort, which checks for neighboring elements, selection sort picks a new item from the array (starting from 0 and going until N) comparing whether there are any other numbers smaller (or larger, depending on the kind of sort being implemented) than the one currently being held. If there is, then they swap places.

## Pseudocode

{% highlight python linenos %}

A=[10,2,78,23,45,89,39]
FOR I IN RANGE(LEN(A)):
    MIN_ELEMENT = I
     FOR J IN RANGE (I+1, LEN(A)):
        IF(A[MIN_ELEMENT] > A[J]):
              MIN_ELEMENT = J

     TEMP = A[I]
     A[I] = A[MIN_ELEMENT]
    A[MIN_ELEMENT] = TEMP


{% endhighlight %}

## Java

{% highlight java linenos %}

void sort(int arr[]) 
    { 
        int n = arr.length; 
  
        // One by one move boundary of unsorted subarray 
        for (int i = 0; i < n-1; i++) 
        { 
            // Find the minimum element in unsorted array 
            int min_idx = i; 
            for (int j = i+1; j < n; j++) 
                if (arr[j] < arr[min_idx]) 
                    min_idx = j; 
  
            // Swap the found minimum element with the first 
            // element 
            int temp = arr[min_idx]; 
            arr[min_idx] = arr[i]; 
            arr[i] = temp; 
        } 
    } 

{% endhighlight %}