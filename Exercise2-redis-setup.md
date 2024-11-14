# Installing and Setting Up Redis

## Linux

### Installation
1. Update your package lists:
    ```bash
    sudo apt update
    ```
2. Install Redis:
    ```bash
    sudo apt install redis-server
    ```

### Configuration
1. Open the Redis configuration file:
    ```bash
    sudo nano /etc/redis/redis.conf
    ```
2. Find the `supervised` directive and set it to `systemd`:
    ```conf
    supervised systemd
    ```
3. Save and close the file.

### Start Redis
1. Start the Redis service:
    ```bash
    sudo systemctl start redis
    ```
2. Enable Redis to start on boot:
    ```bash
    sudo systemctl enable redis
    ```

### Verify Installation
1. Check the Redis server status:
    ```bash
    sudo systemctl status redis
    ```
2. Test the Redis CLI:
    ```bash
    redis-cli ping
    ```
    You should see `PONG` as the response.

## macOS

### Installation
1. Install Homebrew if you haven't already:
    ```bash
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```
2. Install Redis using Homebrew:
    ```bash
    brew install redis
    ```

### Configuration
1. Open the Redis configuration file:
    ```bash
    nano /usr/local/etc/redis.conf
    ```
2. Find the `supervised` directive and set it to `launchd`:
    ```conf
    supervised launchd
    ```
3. Save and close the file.

### Start Redis
1. Start the Redis service:
    ```bash
    brew services start redis
    ```

### Verify Installation
1. Test the Redis CLI:
    ```bash
    redis-cli ping
    ```
    You should see `PONG` as the response.

## Windows

### Installation
1. Download the latest Redis zip file from the [Redis GitHub repository](https://github.com/microsoftarchive/redis/releases).
2. Extract the zip file to a directory, e.g., `C:\Redis`.

### Configuration
1. Open the Redis configuration file:
    ```bash
    C:\Redis\redis.windows.conf
    ```
2. Modify any settings as needed and save the file.

### Start Redis
1. Open Command Prompt and navigate to the Redis directory:
    ```cmd
    cd C:\Redis
    ```
2. Start the Redis server:
    ```cmd
    redis-server.exe redis.windows.conf
    ```

### Verify Installation
1. Open another Command Prompt window and test the Redis CLI:
    ```cmd
    redis-cli.exe ping
    ```
    You should see `PONG` as the response.
