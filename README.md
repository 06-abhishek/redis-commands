Most important **Redis commands**, categorized by their usage:  

---

### **🔹 Basic Commands**
| Command          | Description | Example |
|-----------------|-------------|---------|
| `SET key value` | Store a value in a key | `SET user "Abhishek"` |
| `GET key` | Retrieve the value of a key | `GET user` → `"Abhishek"` |
| `DEL key` | Delete a key | `DEL user` |
| `EXISTS key` | Check if a key exists (1 = exists, 0 = not found) | `EXISTS user` |
| `EXPIRE key seconds` | Set a key to expire after some time | `EXPIRE user 60` |
| `TTL key` | Check remaining time to live (TTL) | `TTL user` |
| `PERSIST key` | Remove expiration from a key | `PERSIST user` |

---

### **🔹 Expiring Keys**
| Command | Description | Example |
|---------|-------------|---------|
| `SETEX key seconds value` | Set a key with an expiration time | `SETEX temp 30 "test"` |
| `PSETEX key milliseconds value` | Same as `SETEX`, but in milliseconds | `PSETEX temp 5000 "test"` |

---

### **🔹 Hashes (Like Objects in JSON)**
| Command | Description | Example |
|---------|-------------|---------|
| `HSET hash field value` | Set a field in a hash | `HSET user name "Abhishek"` |
| `HGET hash field` | Get a field from a hash | `HGET user name` |
| `HGETALL hash` | Get all fields & values from a hash | `HGETALL user` |
| `HDEL hash field` | Delete a field from a hash | `HDEL user name` |
| `HLEN hash` | Count fields in a hash | `HLEN user` |
| `HEXISTS hash field` | Check if a field exists (1 = exists, 0 = not) | `HEXISTS user name` |

---

### **🔹 Lists (Like Arrays)**
| Command | Description | Example |
|---------|-------------|---------|
| `LPUSH list value` | Add value to the **left** (beginning) | `LPUSH queue "task1"` |
| `RPUSH list value` | Add value to the **right** (end) | `RPUSH queue "task2"` |
| `LPOP list` | Remove & return first element | `LPOP queue` → `"task1"` |
| `RPOP list` | Remove & return last element | `RPOP queue` → `"task2"` |
| `LLEN list` | Get the length of the list | `LLEN queue` |

---

### **🔹 Sets (Unique Unordered Values)**
| Command | Description | Example |
|---------|-------------|---------|
| `SADD set value` | Add a value to a set | `SADD myset "A"` |
| `SMEMBERS set` | Get all values in a set | `SMEMBERS myset` |
| `SREM set value` | Remove a value from a set | `SREM myset "A"` |
| `SCARD set` | Get the number of values in a set | `SCARD myset` |

---

### **🔹 Sorted Sets (Unique Ordered Values)**
| Command | Description | Example |
|---------|-------------|---------|
| `ZADD zset score value` | Add value with a score | `ZADD leaderboard 100 "player1"` |
| `ZRANGE zset start stop` | Get values in a range (by index) | `ZRANGE leaderboard 0 -1` |
| `ZRANK zset value` | Get rank of a value | `ZRANK leaderboard "player1"` |

---

### **🔹 Transactions (Atomic Operations)**
| Command | Description | Example |
|---------|-------------|---------|
| `MULTI` | Start a transaction | `MULTI` |
| `EXEC` | Execute all commands in the transaction | `EXEC` |
| `DISCARD` | Cancel a transaction | `DISCARD` |

---

### **🔹 Pub/Sub (Messaging)**
| Command | Description | Example |
|---------|-------------|---------|
| `PUBLISH channel message` | Send a message to a channel | `PUBLISH news "Hello"` |
| `SUBSCRIBE channel` | Subscribe to a channel | `SUBSCRIBE news` |

---

### **🔹 Keys & Scan Commands**
| Command | Description | Example |
|---------|-------------|---------|
| `KEYS pattern` | Get all matching keys (not recommended for production) | `KEYS *` |
| `SCAN cursor MATCH pattern` | Scan keys (better than `KEYS`) | `SCAN 0 MATCH user:*` |
| `FLUSHDB` | Delete all keys in the current database | `FLUSHDB` |
| `FLUSHALL` | Delete all keys in all databases | `FLUSHALL` |
