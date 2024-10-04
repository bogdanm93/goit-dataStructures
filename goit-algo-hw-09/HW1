import time

# Available coin denominations
DENOMINATIONS = [50, 25, 10, 5, 2, 1]

def greedy_coin_selection(amount):
    coin_distribution = {}
    for coin in DENOMINATIONS:
        if amount == 0:
            break
        count = amount // coin
        if count > 0:
            coin_distribution[coin] = count
            amount -= coin * count
    return coin_distribution

def min_coins_dynamic(amount):
    # Initialize the table for dynamic programming
    min_coins = [float('inf')] * (amount + 1)
    min_coins[0] = 0
    coins_used = [0] * (amount + 1)
    
    for current_amount in range(1, amount + 1):
        for coin in DENOMINATIONS:
            if current_amount >= coin and min_coins[current_amount - coin] + 1 < min_coins[current_amount]:
                min_coins[current_amount] = min_coins[current_amount - coin] + 1
                coins_used[current_amount] = coin
    
    # Backtrack to determine the coins used
    coin_distribution = {}
    while amount > 0:
        coin = coins_used[amount]
        if coin in coin_distribution:
            coin_distribution[coin] += 1
        else:
            coin_distribution[coin] = 1
        amount -= coin
    
    return coin_distribution

def performance_comparison(amount):
    start_time = time.time()
    greedy_result = greedy_coin_selection(amount)
    greedy_time = time.time() - start_time
    
    start_time = time.time()
    dp_result = min_coins_dynamic(amount)
    dp_time = time.time() - start_time
    
    print(f"Greedy Algorithm for {amount}: {greedy_result} (Time: {greedy_time:.6f} seconds)")
    print(f"Dynamic Programming for {amount}: {dp_result} (Time: {dp_time:.6f} seconds)")

# Example usage
example_amount = 113
print("Greedy Algorithm result:", greedy_coin_selection(example_amount))
print("Dynamic Programming result:", min_coins_dynamic(example_amount))

# Compare performance for a larger amount
performance_comparison(10000)