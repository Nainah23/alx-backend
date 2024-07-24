# Caching Systems

This repository contains different caching systems implemented in Python. Each caching system follows a specific cache replacement policy. The project includes the following caching systems:

1. **Basic Cache**
2. **FIFO Cache**
3. **LIFO Cache**
4. **LRU Cache**
5. **MRU Cache**
6. **LFU Cache**

## Repository Structure

```
.
├── 0-main.py
├── 0-basic_cache.py
├── 1-main.py
├── 1-fifo_cache.py
├── 2-main.py
├── 2-lifo_cache.py
├── 3-main.py
├── 3-lru_cache.py
├── 4-main.py
├── 4-mru_cache.py
├── 100-main.py
└── 100-lfu_cache.py
```

## Caching Systems

### Basic Cache
A simple caching system with no limit on the number of items. The `BasicCache` class inherits from `BaseCaching`.

- **File:** `0-basic_cache.py`
- **Main:** `0-main.py`

```python
class BasicCache(BaseCaching):
    def put(self, key, item):
        # Add an item to the cache
        pass

    def get(self, key):
        # Get an item from the cache
        pass
```

### FIFO Cache
A caching system that uses the First-In-First-Out (FIFO) replacement policy. The `FIFOCache` class inherits from `BaseCaching`.

- **File:** `1-fifo_cache.py`
- **Main:** `1-main.py`

```python
class FIFOCache(BaseCaching):
    def put(self, key, item):
        # Add an item to the cache with FIFO policy
        pass

    def get(self, key):
        # Get an item from the cache
        pass
```

### LIFO Cache
A caching system that uses the Last-In-First-Out (LIFO) replacement policy. The `LIFOCache` class inherits from `BaseCaching`.

- **File:** `2-lifo_cache.py`
- **Main:** `2-main.py`

```python
class LIFOCache(BaseCaching):
    def put(self, key, item):
        # Add an item to the cache with LIFO policy
        pass

    def get(self, key):
        # Get an item from the cache
        pass
```

### LRU Cache
A caching system that uses the Least Recently Used (LRU) replacement policy. The `LRUCache` class inherits from `BaseCaching`.

- **File:** `3-lru_cache.py`
- **Main:** `3-main.py`

```python
class LRUCache(BaseCaching):
    def put(self, key, item):
        # Add an item to the cache with LRU policy
        pass

    def get(self, key):
        # Get an item from the cache
        pass
```

### MRU Cache
A caching system that uses the Most Recently Used (MRU) replacement policy. The `MRUCache` class inherits from `BaseCaching`.

- **File:** `4-mru_cache.py`
- **Main:** `4-main.py`

```python
class MRUCache(BaseCaching):
    def put(self, key, item):
        # Add an item to the cache with MRU policy
        pass

    def get(self, key):
        # Get an item from the cache
        pass
```

### LFU Cache
A caching system that uses the Least Frequently Used (LFU) replacement policy. The `LFUCache` class inherits from `BaseCaching`.

- **File:** `100-lfu_cache.py`
- **Main:** `100-main.py`

```python
class LFUCache(BaseCaching):
    def put(self, key, item):
        # Add an item to the cache with LFU policy
        pass

    def get(self, key):
        # Get an item from the cache
        pass
```

## Running the Tests

To run the tests, use the following commands:

```bash
python3 0-main.py
python3 1-main.py
python3 2-main.py
python3 3-main.py
python3 4-main.py
python3 100-main.py
```

Each `main.py` file contains test cases for the respective caching system. The output will show the current state of the cache after each operation and any items discarded due to the cache replacement policy.

