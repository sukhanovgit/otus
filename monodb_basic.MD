# Необходимо:

## установить MongoDB одним из способов: ВМ, докер;
curl -fsSL https://pgp.mongodb.com/server-6.0.asc | \
>    sudo gpg -o /usr/share/keyrings/mongodb-server-6.0.gpg \
>    --dearmor
File '/usr/share/keyrings/mongodb-server-6.0.gpg' exists. Overwrite? (y/N) y
root@alismongodb-test:~# sudo apt-get install gnupg
Reading package lists... Done
Building dependency tree
Reading state information... Done
gnupg is already the newest version (2.2.19-3ubuntu2.2).
The following packages were automatically installed and are no longer required:
  libfwupdplugin1 libxmlb1 linux-headers-5.4.0-65 linux-headers-5.4.0-65-generic linux-image-5.4.0-65-generic linux-modules-5.4.0-65-generic linux-modules-extra-5.4.0-65-generic
Use 'sudo apt autoremove' to remove them.
0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.
root@alismongodb-test:~# echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-6.0.gpg ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/6.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-6.0.list
deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-6.0.gpg ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/6.0 multiverse
root@alismongodb-test:~# apt update
Get:1 http://repo.zabbix.com/zabbix/5.0/ubuntu focal InRelease [4,958 B]
Ign:2 https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/6.0 InRelease
Hit:3 http://archive.ubuntu.com/ubuntu focal InRelease
Get:4 https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/6.0 Release [3,094 B]
Get:5 http://archive.ubuntu.com/ubuntu focal-updates InRelease [114 kB]
Get:6 http://repo.zabbix.com/zabbix/5.0/ubuntu focal/main Sources [1,198 B]
Get:7 https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/6.0 Release.gpg [801 B]
Get:8 http://repo.zabbix.com/zabbix/5.0/ubuntu focal/main amd64 Packages [4,790 B]
Get:9 https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/6.0/multiverse amd64 Packages [17.8 kB]
Get:10 https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/6.0/multiverse arm64 Packages [15.9 kB]
Get:11 http://archive.ubuntu.com/ubuntu focal-backports InRelease [108 kB]
Get:12 http://archive.ubuntu.com/ubuntu focal-security InRelease [114 kB]
Get:13 http://archive.ubuntu.com/ubuntu focal-updates/main amd64 Packages [2,498 kB]
Get:14 http://archive.ubuntu.com/ubuntu focal-updates/main Translation-en [424 kB]
Get:15 http://archive.ubuntu.com/ubuntu focal-updates/main amd64 c-n-f Metadata [16.4 kB]
Get:16 http://archive.ubuntu.com/ubuntu focal-updates/restricted amd64 Packages [1,776 kB]
Get:17 http://archive.ubuntu.com/ubuntu focal-updates/restricted Translation-en [249 kB]
Get:18 http://archive.ubuntu.com/ubuntu focal-updates/restricted amd64 c-n-f Metadata [636 B]
Get:19 http://archive.ubuntu.com/ubuntu focal-updates/universe amd64 Packages [1,051 kB]
Get:20 http://archive.ubuntu.com/ubuntu focal-updates/universe Translation-en [248 kB]
Get:21 http://archive.ubuntu.com/ubuntu focal-updates/universe amd64 c-n-f Metadata [24.2 kB]
Get:22 http://archive.ubuntu.com/ubuntu focal-updates/multiverse amd64 Packages [25.2 kB]
Get:23 http://archive.ubuntu.com/ubuntu focal-updates/multiverse Translation-en [7,408 B]
Get:24 http://archive.ubuntu.com/ubuntu focal-updates/multiverse amd64 c-n-f Metadata [612 B]
Get:25 http://archive.ubuntu.com/ubuntu focal-backports/main amd64 Packages [45.7 kB]
Get:26 http://archive.ubuntu.com/ubuntu focal-backports/main amd64 c-n-f Metadata [1,420 B]
Get:27 http://archive.ubuntu.com/ubuntu focal-backports/universe amd64 Packages [24.9 kB]
Get:28 http://archive.ubuntu.com/ubuntu focal-backports/universe Translation-en [16.3 kB]
Get:29 http://archive.ubuntu.com/ubuntu focal-backports/universe amd64 c-n-f Metadata [880 B]
Get:30 http://archive.ubuntu.com/ubuntu focal-security/main amd64 Packages [2,114 kB]
Get:31 http://archive.ubuntu.com/ubuntu focal-security/main Translation-en [341 kB]
Get:32 http://archive.ubuntu.com/ubuntu focal-security/main amd64 c-n-f Metadata [12.5 kB]
Get:33 http://archive.ubuntu.com/ubuntu focal-security/restricted amd64 Packages [1,667 kB]
Get:34 http://archive.ubuntu.com/ubuntu focal-security/restricted Translation-en [235 kB]
Get:35 http://archive.ubuntu.com/ubuntu focal-security/restricted amd64 c-n-f Metadata [640 B]
Get:36 http://archive.ubuntu.com/ubuntu focal-security/universe amd64 Packages [825 kB]
Get:37 http://archive.ubuntu.com/ubuntu focal-security/universe Translation-en [166 kB]
Get:38 http://archive.ubuntu.com/ubuntu focal-security/universe amd64 c-n-f Metadata [17.6 kB]
Get:39 http://archive.ubuntu.com/ubuntu focal-security/multiverse amd64 Packages [22.9 kB]
Get:40 http://archive.ubuntu.com/ubuntu focal-security/multiverse Translation-en [5,488 B]
Get:41 http://archive.ubuntu.com/ubuntu focal-security/multiverse amd64 c-n-f Metadata [540 B]
Fetched 12.2 MB in 1min 1s (198 kB/s)
Reading package lists... Done
Building dependency tree
Reading state information... Done
98 packages can be upgraded. Run 'apt list --upgradable' to see them.
root@alismongodb-test:~# apt-get install -y mongodb-org
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following packages were automatically installed and are no longer required:
  libfwupdplugin1 libxmlb1 linux-headers-5.4.0-65 linux-headers-5.4.0-65-generic linux-image-5.4.0-65-generic linux-modules-5.4.0-65-generic linux-modules-extra-5.4.0-65-generic
Use 'apt autoremove' to remove them.
The following additional packages will be installed:
  mongodb-database-tools mongodb-mongosh mongodb-org-database mongodb-org-database-tools-extra mongodb-org-mongos mongodb-org-server mongodb-org-shell mongodb-org-tools
The following NEW packages will be installed:
  mongodb-database-tools mongodb-mongosh mongodb-org mongodb-org-database mongodb-org-database-tools-extra mongodb-org-mongos mongodb-org-server mongodb-org-shell mongodb-org-tools
0 upgraded, 9 newly installed, 0 to remove and 98 not upgraded.
Need to get 142 MB of archives.
After this operation, 422 MB of additional disk space will be used.
Get:1 https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/6.0/multiverse amd64 mongodb-database-tools amd64 100.7.0 [50.6 MB]
Get:2 https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/6.0/multiverse amd64 mongodb-mongosh amd64 1.8.0 [41.4 MB]
Get:3 https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/6.0/multiverse amd64 mongodb-org-shell amd64 6.0.5 [3,084 B]
Get:4 https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/6.0/multiverse amd64 mongodb-org-server amd64 6.0.5 [29.0 MB]
Get:5 https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/6.0/multiverse amd64 mongodb-org-mongos amd64 6.0.5 [20.5 MB]
Get:6 https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/6.0/multiverse amd64 mongodb-org-database-tools-extra amd64 6.0.5 [7,756 B]
Get:7 https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/6.0/multiverse amd64 mongodb-org-database amd64 6.0.5 [3,540 B]
Get:8 https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/6.0/multiverse amd64 mongodb-org-tools amd64 6.0.5 [2,892 B]
Get:9 https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/6.0/multiverse amd64 mongodb-org amd64 6.0.5 [2,932 B]
Fetched 142 MB in 2min 53s (820 kB/s)
Selecting previously unselected package mongodb-database-tools.
(Reading database ... 145128 files and directories currently installed.)
Preparing to unpack .../0-mongodb-database-tools_100.7.0_amd64.deb ...
Unpacking mongodb-database-tools (100.7.0) ...
Selecting previously unselected package mongodb-mongosh.
Preparing to unpack .../1-mongodb-mongosh_1.8.0_amd64.deb ...
Unpacking mongodb-mongosh (1.8.0) ...
Selecting previously unselected package mongodb-org-shell.
Preparing to unpack .../2-mongodb-org-shell_6.0.5_amd64.deb ...
Unpacking mongodb-org-shell (6.0.5) ...
Selecting previously unselected package mongodb-org-server.
Preparing to unpack .../3-mongodb-org-server_6.0.5_amd64.deb ...
Unpacking mongodb-org-server (6.0.5) ...
Selecting previously unselected package mongodb-org-mongos.
Preparing to unpack .../4-mongodb-org-mongos_6.0.5_amd64.deb ...
Unpacking mongodb-org-mongos (6.0.5) ...
Selecting previously unselected package mongodb-org-database-tools-extra.
Preparing to unpack .../5-mongodb-org-database-tools-extra_6.0.5_amd64.deb ...
Unpacking mongodb-org-database-tools-extra (6.0.5) ...
Selecting previously unselected package mongodb-org-database.
Preparing to unpack .../6-mongodb-org-database_6.0.5_amd64.deb ...
Unpacking mongodb-org-database (6.0.5) ...
Selecting previously unselected package mongodb-org-tools.
Preparing to unpack .../7-mongodb-org-tools_6.0.5_amd64.deb ...
Unpacking mongodb-org-tools (6.0.5) ...
Selecting previously unselected package mongodb-org.
Preparing to unpack .../8-mongodb-org_6.0.5_amd64.deb ...
Unpacking mongodb-org (6.0.5) ...
Setting up mongodb-mongosh (1.8.0) ...
Setting up mongodb-org-server (6.0.5) ...
Adding system user `mongodb' (UID 116) ...
Adding new user `mongodb' (UID 116) with group `nogroup' ...
Not creating home directory `/home/mongodb'.
Adding group `mongodb' (GID 120) ...
Done.
Adding user `mongodb' to group `mongodb' ...
Adding user mongodb to group mongodb
Done.
Setting up mongodb-org-shell (6.0.5) ...
Setting up mongodb-database-tools (100.7.0) ...
Setting up mongodb-org-mongos (6.0.5) ...
Setting up mongodb-org-database-tools-extra (6.0.5) ...
Setting up mongodb-org-database (6.0.5) ...
Setting up mongodb-org-tools (6.0.5) ...
Setting up mongodb-org (6.0.5) ...
Processing triggers for man-db (2.9.1-1) ...
root@alismongodb-test:~# ulimit -n 64000 && ulimit -u 64000 && ulimit -t unlimited && ulimit -v unlimited && ulimit -l unlimited && ulimit -m unlimited
root@alismongodb-test:~# mongosh --port 27017
Current Mongosh Log ID: 643fc2d64776a5e2d296d3db
root@alismongodb-test:~# sudo systemctl start mongod
![image](https://user-images.githubusercontent.com/102989024/233048364-ee533e62-c1bf-4d7e-8045-8cf0d9ce8b87.png)

заполнить данными;
написать несколько запросов на выборку и обновление данных
