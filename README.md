BY RECURSION


class Solution {
    
    public int countWays(int coins[], int sum) {
        return count(coins.length, coins, sum);
    }

    int count(int n, int coins[], int sum) {
        if (sum == 0) return 1; // Base case: Found a valid combination
        if (n == 0 || sum < 0) return 0; // No more coins or negative sum
        
        int include = count(n, coins, sum - coins[n - 1]); // Use current coin
        int exclude = count(n - 1, coins, sum); // Skip current coin
        
        return include + exclude;
    }
}
