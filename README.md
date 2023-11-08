# Java-Program-for-finding-the-largest-element-of-the-array

Largest Element of the array using Java
Here, in this page we will discuss the program to find the largest element of the array using java. We are given with an array and we need to print the largest element among the given elements of the array.

Java program for finding the largest number in the array
Here, we will discuss the following methods to find the maximum element of the array.

Method 1 : Using Iteration
Method 2 : Using recursion Top-down Approach
Method 3 : Bottom-up approach
Method 1 :
Declare a variable say max and initialize it with array first element.
Run a loop from index 1 to N, and check
If arr[i]>max, then set max = arr[i]
After complete iteration print max.
Method 1 : code in Java
Run
import java.util.Scanner;

public class Main
{
  public static void main(String args[])
  {

     int arr[] = {12, 13, 1, 10, 34, 10};

     int max = arr[0];

     for(int i=0; i<arr.length; i++)
     {
       if(max < arr[i])
       {
          max = arr[i];
       }

     }

    System.out.print(max); 
  }
}
Output :
34
Related Pages
Given a set of positive integers, find all its subsets
 
Given a string s, remove all its adjacent duplicate characters recursively
 
Find Smallest Element in an Array

Find the Smallest and largest element in an array

Find Second Smallest Element in an Array

Method 2 :
Create a recursive function say getmax(int arr[], int n)
Base Condition : if(n==1) return arr[0]
Otherwise, return max(arr[n-1], getmax(arr, n-1))
Largest Element of the array using java
Method 2 : Code in Java
Run

import java.util.Scanner;
import java.util.*;

public class Main
{ 
   static int getmax(int arr[], int n){
       if(n==1)
       return arr[0];

       return Math.max(arr[n-1], getmax(arr, n-1));
   }
   public static void main(String args[])
   {

      int arr[] = {12, 13, 1, 10, 34, 10};
      int n = arr.length;
      System.out.print(getmax(arr, n)); 
   }
}
Output :
34
Method 3 :
Call a function : maximum(int arr[], int i, int end)

With initial call up values as maximum(arr, 0, end)
Initially passing end as the index of last array element
Initially passing ‘i’ as 0
Recursively reach iteration where reading 2nd last element
Find larger between 2nd last and last array elements
And return the result to max value of the previous recursive iteration
In each of the remaining recursive callups find the largest b/w current array index element and current max value
Pass final max value from last recursive callup to main and print
Method 3 : Code in Java
Run
import java.util.Scanner;
import java.util.*;

public class Main
{ 
   static int maximum(int arr[], int i, int end)
   {
      int max;

      // when we reach 2nd last array element
      // return the larger b/w last & 2nd last elements
      if(i == end-1)
         return (arr[i] > arr[i + 1]) ? arr[i] : arr[i + 1];

      max = maximum(arr, i + 1, end);

      return (arr[i] > max) ? arr[i] : max;
   }

   public static void main(String args[])
   {

     int arr[] = {12, 13, 1, 10, 34, 10};
     int end = arr.length-1;
     System.out.print(maximum(arr, 0, end)); 
   }
}
