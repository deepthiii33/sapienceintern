# Linux Administration Tasks Final  Report

This report documents the Linux administrative tasks performed along with the corresponding commands.

## 1. Create a directory named `my_project` and navigate into it.
      mkdir my_project
      cd my_project
 
  ![](https://github.com/deepthiii33/sapienceintern/blob/main/task2/screenshots/creating_naviagting_directory.png)

## 2. Create an empty file named `notes.txt`
        touch notes.txt

 ![](https://github.com/deepthiii33/sapienceintern/blob/main/task2/screenshots/create_empty_file.png)

## 3. Copy `notes.txt` to a new file named `backup_notes.txt`, then move it into a newly created subdirectory called *backup*
      mkdir backup
      cp notes.txt backup_notes.txt
      mv backup_notes.txt backup/

![](https://github.com/deepthiii33/sapienceintern/blob/main/task2/screenshots/copy_move.png)

## 4. Delete the `backup` directory along with its contents.
     rm -r backup

![](https://github.com/deepthiii33/sapienceintern/blob/main/task2/screenshots/delete_files.png)
## 5. Create a file named `script.sh`, grant it executable permissions, and change its permissions so it is readable and executable only by the file owner.
     touch script.sh
     chmod 700 script.sh

![](https://github.com/deepthiii33/sapienceintern/blob/main/task2/screenshots/create_script_file.png)

## 6. Update your package manager's repository list, install the *htop* package, verify its installation, and then uninstall it.
     sudo apt update  # For Debian/Ubuntu
     sudo apt install htop -y

 ![](https://github.com/deepthiii33/sapienceintern/blob/main/task2/screenshots/update_install_htop.png)

     htop --version
     sudo apt remove htop -y

![](https://github.com/deepthiii33/sapienceintern/blob/main/task2/screenshots/remove_htop.png)

## 7. Check all running processes, identify the PID of a specific process (e.g., *sleep* if running), and terminate it using the `kill` command.
    - ps aux | grep sleep
    - kill <PID>

![](https://github.com/deepthiii33/sapienceintern/blob/main/task2/screenshots/running_processes_sleep.png)

## 8. Display your machine's IP address, ping google.com to verify connectivity, and list all active network connections.
       ip a

![](https://github.com/deepthiii33/sapienceintern/blob/main/task2/screenshots/ip_addr.png)
 ##### Here my IP  address is : 192.168.1.11##### 
      ping -c 4 google.com

![](https://github.com/deepthiii33/sapienceintern/blob/main/task2/screenshots/ping_command_working.png)
   
          netstat -tulnp

![](https://github.com/deepthiii33/sapienceintern/blob/main/task2/screenshots/netstat%20%E2%80%93tulnp.png)

## 9. Add a new user named `test`, switch to this user, and grant them sudo privileges.
     sudo useradd -m test
     sudo usermod -aG sudo testuser
     su - test
![](https://github.com/deepthiii33/sapienceintern/blob/main/task2/screenshots/new_user_permission.png)

## 10. Write a shell script named `hello.sh` that outputs "Hello, World!" when executed.
      echo -e "#!/bin/bash\necho "Hello, World!"" > hello.sh
      chmod +x hello.sh

![](https://github.com/deepthiii33/sapienceintern/blob/main/task2/screenshots/hello.sh.png)

    ./hello.sh
![](https://github.com/deepthiii33/sapienceintern/blob/main/task2/screenshots/exec_hello.sh.png)

## 11. Create a tarball of the `my_project` directory, extract its contents, and compress the tarball using `gzip`.
    tar -cvf my_project.tar my_project/
    tar -xvf my_project.tar
    gzip my_project.tar

![](https://github.com/deepthiii33/sapienceintern/blob/main/task2/screenshots/file_archieve_compression.png)

## 12. Check the disk usage, memory usage, and CPU information of your system.
    df -h
    free -h
![](https://github.com/deepthiii33/sapienceintern/blob/main/task2/screenshots/Resource%20Monitoring.png)
   
    lscpu
![](https://github.com/deepthiii33/sapienceintern/blob/main/task2/screenshots/Lscpu.png)


**This report provides a structured approach to executing fundamental Linux administrative tasks, covering file management, user administration, networking, and system monitoring. The included commands and screenshots document each step.Learning these basic commands is essential for managing and troubleshooting a Linux system effectively**
