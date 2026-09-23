# Exercise 5 — Comment Rescue

Below is a working method with no comments. It runs fine. It is also very hard to understand.

```java
public static double calc(double p, int y, double r) {
    double t = p;
    for (int i = 0; i < y; i++) {
        t = t + (t * r);
    }
    return t - p;
}
```

## Part A — Figure out what it does

**1. What do you think `p`, `y`, and `r` represent?**
P means the initial amount
Y means the number of years
R means the interest rate per year


**2. What does the method return?**
The method returns the total interest or growth earned over the specified number of years. It repeatedly increases the current amount by the given rate, then subtracts the original principal from the final amount.


**3. What would you rename each variable and the method itself?**

| Original | Better name |
|---|---|
| `calc` |Calculate interest Earned|
| `p` |Principal|
| `y` |Years|
| `r` |Interest Rate|
| `t` |Current Amount|

## Part B — Rewrite it

Rewrite the method with better names **and** comments. Remember the rule:

> **Bad comments explain *what*. Good comments explain *why*.**

```java
// // Calculate the total interest earned through annual compounding.
public static double calculateInterestEarned(
        double principal, int years, double interestRate) {

    double currentAmount = principal;

    // Compound the balance once for each year so that
    // each year's interest also earns interest in later years.
    for (int year = 0; year < years; year++) {
        currentAmount = currentAmount + (currentAmount * interestRate);
    }

    // Remove the original principal to return only the interest earned.
    return currentAmount - principal;
}
```

## Part C — Reflect

**Which helped a future reader more — the better variable names, or the comments? Defend your answer in two or three sentences.**
The better variable names helped me more because they make the code understandable without needing to read a comment. Good comments are still useful for explaining why the amount is updated each year and why the principal is subtracted at the end. Together, clear names and useful comments make the method easier for a future reader to understand.

> There's no single right answer here. Most professionals would say good names reduce the *need* for comments, and comments should then explain the things names can't — assumptions, edge cases, and why a decision was made.
