---

# Redis Queuing System in Node.js

This project demonstrates a basic queuing system using Redis in Node.js. It includes Redis setup, client operations, and implementing a queue system with Kue.

## Table of Contents
- [Installation](#installation)
- [Task 0: Install Redis Instance](#task-0-install-redis-instance)
- [Task 1: Node Redis Client](#task-1-node-redis-client)
- [Task 2: Basic Redis Operations](#task-2-basic-redis-operations)
- [Task 3: Async Redis Operations](#task-3-async-redis-operations)
- [Task 4: Advanced Redis Operations](#task-4-advanced-redis-operations)
- [Task 5: Redis Publisher and Subscriber](#task-5-redis-publisher-and-subscriber)
- [Task 6: Create the Job Creator](#task-6-create-the-job-creator)
- [Task 7: Create the Job Processor](#task-7-create-the-job-processor)

## Installation

1. **Clone the repository:**
    ```bash
    git clone https://github.com/your-username/alx-backend.git
    cd alx-backend/0x03-queuing_system_in_js
    ```

2. **Install Redis:**
    Download, extract, and compile the latest stable Redis version (higher than 5.0.7):
    ```bash
    wget http://download.redis.io/releases/redis-6.0.10.tar.gz
    tar xzf redis-6.0.10.tar.gz
    cd redis-6.0.10
    make
    ```

3. **Start Redis Server:**
    ```bash
    src/redis-server &
    ```

4. **Install Node.js dependencies:**
    ```bash
    npm install
    ```

## Task 0: Install Redis Instance

1. **Start Redis in the background:**
    ```bash
    src/redis-server &
    ```
2. **Ping the Redis server:**
    ```bash
    src/redis-cli ping
    ```
   Expected output: `PONG`

3. **Set and Get Redis keys:**
    ```bash
    127.0.0.1:[Port]> set Holberton School
    127.0.0.1:[Port]> get Holberton
    ```
   Expected output: `"School"`

4. **Kill the Redis server:**
    ```bash
    kill [PID_OF_Redis_Server]
    ```

5. **Copy the `dump.rdb` file:**
    - Copy the `dump.rdb` from the Redis directory to the root of the Queuing project.

## Task 1: Node Redis Client

- **Install `node_redis`:**
    ```bash
    npm install redis
    ```
- **Script `0-redis_client.js`:** Connect to Redis and handle connection success or failure.
    ```bash
    npm run dev 0-redis_client.js
    ```

## Task 2: Basic Redis Operations

- **Script `1-redis_op.js`:** Set and retrieve Redis keys using callbacks.
    ```bash
    npm run dev 1-redis_op.js
    ```

## Task 3: Async Redis Operations

- **Script `2-redis_op_async.js`:** Use `promisify` and `async/await` for Redis operations.
    ```bash
    npm run dev 2-redis_op_async.js
    ```

## Task 4: Advanced Redis Operations

- **Script `4-redis_advanced_op.js`:** Store and retrieve hash values in Redis.
    ```bash
    npm run dev 4-redis_advanced_op.js
    ```

## Task 5: Redis Publisher and Subscriber

- **Scripts `5-subscriber.js` and `5-publisher.js`:** Implement a basic Redis-based queuing system.
    ```bash
    npm run dev 5-subscriber.js
    npm run dev 5-publisher.js
    ```

## Task 6: Create the Job Creator

- **Script `6-job_creator.js`:** Create jobs in a Redis queue using Kue.
    ```bash
    npm run dev 6-job_creator.js
    ```

## Task 7: Create the Job Processor

- **Script `6-job_processor.js`:** Process jobs from a Redis queue using Kue.
    ```bash
    npm run dev 6-job_processor.js
    ```

## Author

- **Ian Wainaina Kamau**

---
