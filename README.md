# CPP-Program-to-Find-Prime-Number-between-1-to-100

Prime number between 1 to 100 in C++
We will discuss the program for Prime number between 1 to 100 in C++. A prime number is an positive integer that has no integer factors except one and itself or can only be exactly divided by the integers 1 and itself without leaving a remainder.
For example 73 is prime, because it can only be divided by 1 and 73.So prime number has two factor one is 1 another is number itself is called prime number.

The number 1 is neither prime nor composite.

Methods Discussed in page
Method 1 : Basic checking prime by only checking first n
Method 2 : Basic checking prime by only checking first n/2 divisors
Method 3 : Checking prime by only checking first √n divisors
Method 4 :Checking prime by only checking first √n divisors, but also skipping even iterations.
Method 1
Set lower bound = 1, upper bound = 100
Run a loop in the iteration of (i) b/w these bounds.
For each, i check if its prime or not using function checkPrime(i)
If i is prime print it else move to next iteration
Method 1 : Code in C++
Run
#include <iostream>
using namespace std;

int checkPrime(int num)
{
    if(num < 2){
        return 0;
    }
    else{   
       int x = num/2;
        for(int i = 2; i < x; i++)
        {
            if(num % i == 0)
            {
                return 0;
            }
        }
    }
    
    return 1;
}

int main()
{
    int a = 1, b = 100;
    
    for(int i=a; i <= b; i++){
        if(checkPrime(i))
            cout<<i<<" ";
    }
 
    return 0;
}
//Time Complexity: O(N^2)
//Space Complexity O(1)
Output
2 3 4 5 7 11 13 17 19 23 29 31 37 41 43 47 53 59 61 67 71 73 79 83 89 97 
While loop in C
Method 2
Run a loop in the iteration of (i) b/w 1 and 100 bounds.
For each, i check if its prime or not using function checkPrime(i)
If i is prime print it else move to the next iteration
Method 2 : Code in C++
Run
#include<bits/stdc++.h>
using namespace std;

int checkPrime(int num)
{
    if(num < 2){
        return 0;
    }
    else{   
       int x = num/2;
        for(int i = 2; i < x; i++)
        {
            if(num % i == 0)
            {
                return 0;
            }
        }
    }
    
    return 1;
}
int main()
{
    int a = 1, b = 100;
    
    for(int i=a; i <= b; i++){
        if(checkPrime(i))
            cout<<i<<" ";
    }
 
    return 0;
}
//Time Complexity: O(N^2)
//Space Complexity O(1)
Output
2 3 4 5 7 11 13 17 19 23 29 31 37 41 43 47 53 59 61 67 71 73 79 83 89 97 
Related Pages
Count possible decoding of a given digit sequence

Find the prime numbers between 1 to 100

Calculate the number of digits in an integer

Convert digit/number to words

Counting number of days in a given month of a year

Method 3
The outer logic remains the same. Only the method to check prime changes to make code more optimized. Has better time complexity of O(√N)

Run a loop in the iteration of (i) b/w 1 and 100 bounds.
For each, i check if its prime or not using function checkPrime(i)
If i is prime print it else move to next iteration
Method 3 : Code in C++
Run
#include<bits/stdc++.h>
using namespace std;

int checkPrime(int num)
{
    if(num < 2){
        return 0;
    }
    else{   
    
        for(int i = 2; i < sqrt(num); i++)
        {
            if(num % i == 0)
            {
                return 0;
            }
        }
    }
    
    return 1;
}

int main()
{
    int a = 1, b = 100;
    
    for(int i=a; i <= b; i++){
        if(checkPrime(i))
            cout<<i<<" ";
    }
 
    return 0;
}
//Time Complexity: O(Nsqrt(N))
//Space Complexity O(1)
Output
2 3 4 5 7 11 13 17 19 23 29 31 37 41 43 47 53 59 61 67 71 73 79 83 89 97 
While loop in C
Method 4
The outer logic remains the same. Only the method to check prime changes to make code more optimized. Has same time complexity of O(√N).

But makes around half lesser checks

Run a loop in the iteration of (i) b/w 1 to 100 bounds.
For each, i check if its prime or not using function checkPrime(i)
If i is prime print it else move to next iteration
Method used to check prime
This method uses the assumption that –

We can simply check all divisors between [2, √num]
2 is the only even prime number
We can skip all even iterations in the loop
Code
#include<stdio.h>
#include<math.h>

int checkPrime(int n)
{
    // 0 and 1 are not prime numbers
    // negative numbers are not prime
    if (n <= 1)
        return 0;

    // special case as 2 is the only even number that is prime
    else if (n == 2)
        return 1;

    // Check if n is a multiple of 2 thus all these won't be prime
    else if (n % 2 == 0)
        return 0;

    // If not, then just check the odds
    for (int i = 3; i <= sqrt(n); i += 2)
    {
        if (n % i == 0)
            return 0;
    }
    
    return 1;
}

int main()
{
    
    for(int i=1; i <= 100; i++){
        if(checkPrime(i))
            printf("%d ",i);
    }
 
    return 0;
}
//Time Complexity: O(N√N)
//Space Complexity O(1)

// This method is obviously faster as makes around half lesser comparision due skipping even iterations in the loop
Output
2 3 4 5 7 11 13 17 19 23 29 31 37 41 43 47 53 59 61 67 71 73 79 83 89 97 
