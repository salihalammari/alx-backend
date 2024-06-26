To install and set up Redis as per your requirements, follow these steps:

### Step 1: Download, Extract, and Compile Redis

 1. Download the latest stable Redis version (6.0.10 as of the provided link):

```bash
wget http://download.redis.io/releases/redis-6.0.10.tar.gz
```
 2. Extract the downloaded tarball:

```bash
tar xzf redis-6.0.10.tar.gz
```

 3. Navigate into the extracted Redis directory:

```bash
cd redis-6.0.10
```

 4. Compile Redis:

```bash
make
```

### Step 2: Start Redis Server

 1. Start Redis server in the background:

```bash
src/redis-server &
```
 2. Verify that Redis server is running:

```bash
src/redis-cli ping
```
 Expected output:
```bash
PONG
```

### Step 3: Set and Verify Key-Value Pair
 1. Use Redis client to set a key-value pair:
```bash
src/redis-cli set Holberton School
```
 Expected output:
```bash
OK
```
 2. Retrieve the value for the key:
```bash
src/redis-cli get Holberton
```
 Expected output:
```arduino
"School"
```

### Step 4: Shutdown Redis Server

 1. Find the process ID (PID) of the Redis server:
```bash
ps aux | grep redis-server
```
Output will show a line containing the process information, including the PID.

 2. Kill the Redis server using its PID (replace [PID_OF_Redis_Server] with the actual PID found):

```bash
kill [PID_OF_Redis_Server]
```
### Step 5: Copy dump.rdb File

 1. Assuming you have a dump.rdb file from a previous Redis instance (e.g., from a directory where Redis was already running, such as redis-5.0.7), copy it to the root directory of your Queuing project.
```bash
cp path/to/redis-5.0.7/dump.rdb /path/to/0x03-queuing_system_in_js/
```
## Verification
Ensure that after copying dump.rdb and starting a new Redis server (if needed), you can still retrieve the value from Redis
```bash
src/redis-server &
src/redis-cli get Holberton
```

