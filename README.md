 ## **Problem Statement :**

Given a string containing digits from 2-9 inclusive, return all possible letter combinations that the number could represent.

A mapping of digits to letters (just like on the telephone buttons) is given below. Note that 1 does not map to any letters.

![Capture.PNG](https://prod-oj-files.s3.ap-south-1.amazonaws.com/upload/6d56e1e18e.png)

**Input Format :**
#### **<u>Input Format</u>**

The input consists of multiple testcases.

The first line of input contains an integer t - the number of testcases.

The next 2*t lines contain the description of the t testcases.

The first line of each testcase contains an integer n, the size of the string.

The second line of each testcase contains a string containing digits from 2-9.

#### **<u>Constraints</u>**

1 <=`t`<= 10

1 <=`n`<= 4

`digits[i]`is a digit in the range`['2', '9']`.



### Difficulty:

Medium

### Prerequisite:

Backtracking,recursion

### Problem Statement:

Given an array of integers, nums, return all the triplets in the given array nums[i], nums[j], nums[k] such that i != j, i != k, and j != k, and nums[i] + nums[j] + nums[k] == 0.

### Hint:

Store the possible string values for digits 0-9 in a vector string array or map.

### Short Explanation:

Start from the first index of string digits and recursively call the solve function

### Detailed Explanation:

Since each digit can possibly mean one of several characters, we'll need to create code that branches down the different paths as we iterate through the input digit string (D).

This quite obviously calls for a depth-first search (DFS) approach as we will check each permutation of characters and store them in our answer array (ans). For a DFS approach we can use one of several options, but a recursive solution is generally the cleanest.

But first, we'll need to set up a lookup table (L) to convert a digit to its possible characters. Since the digits are actually low-indexed integers, we can actually choose between an array or map/dictionary here with little difference.

For our DFS function (dfs), we'll have to feed it the current position (pos) in D as well as the string (str) being built. The function will also need to have access to D, L, and ans.

The DFS function itself is fairly simple. It will push a completed str onto ans, otherwise it will look up the characters that match the current pos, and then fire off new recursive functions down each of those paths.

Once we're done, we should be ready to return ans.

### Pseudo Code

```
    sol = {'2':"abc",'3':"def",'4':"ghi",'5':"jkl",'6':"mno",'7':"pqrs",'8':"tuv",'9':"wxyz"}
    ans=[]
    (int idx,string ad,string digits){
        if(idx>=digits.size()){
            ans.push_back(ad);
            return;
        }
        for(auto x : sol[digits[idx]]){
            ret(idx+1,ad+x,digits);
        }
    }
    sort ans
    Output ans

```

**Time Complexity**:O(4^n)

**Space Complexity**:O(4^n)

