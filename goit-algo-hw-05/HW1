class HashMap:
    def __init__(self, capacity):
        self.capacity = capacity
        self.map = [[] for _ in range(self.capacity)]

    def hash_key(self, key):
        return hash(key) % self.capacity

    def add(self, key, value):
        hash_index = self.hash_key(key)
        key_value_pair = [key, value]

        if self.map[hash_index] is None:
            self.map[hash_index] = [key_value_pair]
            return True
        else:
            for pair in self.map[hash_index]:
                if pair[0] == key:
                    pair[1] = value
                    return True
            self.map[hash_index].append(key_value_pair)
            return True

    def retrieve(self, key):
        hash_index = self.hash_key(key)
        if self.map[hash_index] is not None:
            for pair in self.map[hash_index]:
                if pair[0] == key:
                    return pair[1]
        return None

    def remove(self, key):
        hash_index = self.hash_key(key)
        if self.map[hash_index] is not None:
            for i in range(len(self.map[hash_index])):
                if self.map[hash_index][i][0] == key:
                    self.map[hash_index].pop(i)
                    return True
        return False

# Example usage:
hash_table = HashMap(5)
hash_table.add("apple", 10)
hash_table.add("orange", 20)
hash_table.add("banana", 30)

print(hash_table.retrieve("apple"))   # Should print: 10
print(hash_table.retrieve("orange"))  # Should print: 20
print(hash_table.retrieve("banana"))  # Should print: 30

hash_table.remove("orange")
print(hash_table.retrieve("orange"))  # Should print: None