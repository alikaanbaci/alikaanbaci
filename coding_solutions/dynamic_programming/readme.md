# Dynamic Programming

#### What it is?

It is an optimization when we are using recursion. It says store the results of subproblems, so that we do not have re-calculate them when needed later. 

##### 



Fibonacci Series Brute Force

```java
public class Fibonacci {
    public int fib(int n) {
        if(n == 0) return 0;
        if(n == 1) return 1;
        
        return fib(n-1) + fib(n-2);
    }
}
```



Fibonacci Dynamic Programming

```java
public class Fibonacci {
    private int [] dp;
    private n;
    
    Fibonacci(int n) {
        this.dp = new int[n+1];
        this.n = n;
    }
    
    public int fib(int n) {
        if(n == 0) return 0;
        if(n == 1) return 1;
        // if f(n) has already calculated get result from memory
        if(dp[n] != 0) return dp[n];
        // calculate f(n) and store in memory
        dp[n] = fib(n-1) + fib(n-2);
        
        return dp[n];
    }
}
```

