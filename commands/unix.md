## 📁 File & Directory Management

```bash
ls -lah
```

List files with permissions, sizes, and hidden files (human-readable).

```bash
cd -
```

Switch back to the previous directory.

```bash
mkdir -p app/logs/archive
```

Create nested directories in one command.

```bash
cp -r source/ destination/
```

Copy directories recursively.

```bash
mv oldname newname
```

Rename or move files/directories.

```bash
rm -rf node_modules/
```

Force delete files/directories (⚠️ use carefully).

---

## 🔍 Search & Find

```bash
find . -name "*.log"
```

Find files by name.

```bash
grep -R "error" .
```

Search for text recursively in files.

```bash
grep -n "TODO" file.txt
```

Search with line numbers.

```bash
which php
```

Show full path of a command.

---

## 📊 Disk & System Usage

```bash
df -h
```

Show disk space usage.

```bash
du -sh *
```

Show size of files/directories.

```bash
free -h
```

Check memory usage.

```bash
uptime
```

Show system load and running time.

---

## ⚙️ Process Management

```bash
ps aux
```

List all running processes.

```bash
top
```

Live system process monitor.

```bash
htop
```

Improved interactive process viewer (if installed).

```bash
kill -9 <PID>
```

Force kill a process.

```bash
pkill nginx
```

Kill process by name.

---

## 🌐 Networking

```bash
ip a
```

Show network interfaces and IPs.

```bash
ping google.com
```

Check network connectivity.

```bash
curl -I https://example.com
```

Fetch HTTP headers.

```bash
wget https://example.com/file.zip
```

Download files from the internet.

```bash
netstat -tulpn
```

Show listening ports and services.

---

## 🔐 Permissions & Ownership

```bash
chmod +x script.sh
```

Make a file executable.

```bash
chmod 755 file.sh
```

Set read/write/execute permissions.

```bash
chown user:group file.txt
```

Change file owner and group.

---

## 📦 Archives & Compression

```bash
tar -czvf backup.tar.gz folder/
```

Create a compressed archive.

```bash
tar -xzvf backup.tar.gz
```

Extract a tar archive.

```bash
zip -r app.zip app/
```

Create a zip archive.

```bash
unzip app.zip
```

Extract zip files.

---

## 🧠 Useful One-Liners

```bash
history | grep docker
```

Search command history.

```bash
!! 
```

Run the last command again.

```bash
clear
```

Clear terminal screen.

```bash
watch -n 2 df -h
```

Run a command repeatedly every 2 seconds.

```bash
alias ll='ls -lah'
```

Create command shortcuts.

---

## 🚀 Developer-Friendly Commands

```bash
env
```

List environment variables.

```bash
export APP_ENV=local
```

Set an environment variable.

```bash
source ~/.bashrc
```

Reload shell configuration.

```bash
time php artisan migrate
```

Measure execution time of a command.
