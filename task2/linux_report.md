# Linux Administration Tasks Report

This report documents the Linux administrative tasks performed along with the corresponding commands.

## 1. Create a directory named `my_project` and navigate into it.

mkdir my_project
cd my_project


## 2. Create an empty file named `notes.txt`.
touch notes.txt


## 3. Copy `notes.txt` to a new file named `backup_notes.txt`, then move it into a newly created subdirectory called `backup`.
mkdir backup
cp notes.txt backup_notes.txt
mv backup_notes.txt backup/


## 4. Delete the `backup` directory along with its contents.
rm -r backup


## 5. Create a file named `script.sh`, grant it executable permissions, and change its permissions so it is readable and executable only by the file owner.
touch script.sh
chmod u+x script.sh
chmod 700 script.sh

## 6. Update your package manager's repository list, install the `htop` package, verify its installation, and then uninstall it.
sudo apt update  # For Debian/Ubuntu
sudo apt install htop -y
htop --version
sudo apt remove htop -y


## 7. Check all running processes, identify the PID of a specific process (e.g., `sleep` if running), and terminate it using the `kill` command.
ps aux | grep sleep
kill <PID>

## 8. Display your machine's IP address, ping google.com to verify connectivity, and list all active network connections.
ip a
ping -c 4 google.com
netstat -tulnp

## 9. Add a new user named `testuser`, switch to this user, and grant them sudo privileges.
sudo useradd -m testuser
sudo passwd testuser
sudo usermod -aG sudo testuser
su - testuser


## 10. Write a shell script named `hello.sh` that outputs "Hello, World!" when executed.
echo -e "#!/bin/bash\necho \"Hello, World!\"" > hello.sh
chmod +x hello.sh
./hello.sh


## 11. Create a tarball of the `my_project` directory, extract its contents, and compress the tarball using `gzip`.
tar -cvf my_project.tar my_project/
tar -xvf my_project.tar
gzip my_project.tar

## 12. Check the disk usage, memory usage, and CPU information of your system.
df -h
free -m
lscpu




