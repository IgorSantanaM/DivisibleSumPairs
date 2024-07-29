# Divisible Sum Pairs

This repository contains a solution to the HackerRank problem "Divisible Sum Pairs". The goal of the problem is to count the number of pairs in an array where the sum of the elements in the pair is divisible by a given integer.

## Problem Statement

Given an array of integers and a positive integer `k`, find the number of (i, j) pairs where `i < j` and `ar[i] + ar[j]` is divisible by `k`.

### Function Signature

```csharp
public static int divisibleSumPairs(int n, int k, List<int> ar)
```
`n` (INTEGER): The number of elements in the array.
`k` (INTEGER): The integer divisor.
`ar` (INTEGER_ARRAY): The array of integers.
## Returns
`int`: The number of pairs (i, j) where i < j and (ar[i] + ar[j]) % k == 0.
## Example
```
6 3
1 3 2 6 1 2
```
## Output
`5`
*Explanation*
There are 5 pairs whose sums are divisible by 3:
`(1, 2)
(1, 2)
(3, 6)
(2, 1)
(2, 1)`
## Code
``` csharp
using System.CodeDom.Compiler;
using System.Collections.Generic;
using System.Collections;
using System.ComponentModel;
using System.Diagnostics.CodeAnalysis;
using System.Globalization;
using System.IO;
using System.Linq;
using System.Reflection;
using System.Runtime.Serialization;
using System.Text.RegularExpressions;
using System.Text;
using System;

class Result
{
    public static int divisibleSumPairs(int n, int k, List<int> ar)
    {
        int numPairs = 0;
        for (int i = 0; i < n - 1; i++)
        {
            for (int j = i + 1; j < n; j++)
            {
                if ((ar[i] + ar[j]) % k == 0)
                {
                    numPairs++;
                }
            }
        }
        return numPairs;
    }
}

class Solution
{
    public static void Main(string[] args)
    {
        TextWriter textWriter = new StreamWriter(@System.Environment.GetEnvironmentVariable("OUTPUT_PATH"), true);

        string[] firstMultipleInput = Console.ReadLine().TrimEnd().Split(' ');

        int n = Convert.ToInt32(firstMultipleInput[0]);
        int k = Convert.ToInt32(firstMultipleInput[1]);

        List<int> ar = Console.ReadLine().TrimEnd().Split(' ').ToList().Select(arTemp => Convert.ToInt32(arTemp)).ToList();

        int result = Result.divisibleSumPairs(n, k, ar);

        textWriter.WriteLine(result);

        textWriter.Flush();
        textWriter.Close();
    }
}
```
## Usage
To run the program, compile and execute the Solution class. Provide the input via the console in the specified format:
## Example Input
```
6 3
1 3 2 6 1 2
```
Example Output
```
5
```

Feel fre to clone the repo and contribute.
