## 🔬 Lab 4

### Step 1: Archivelog mode

- Show your archiving status then enable the archiving mode if not enabled and show your archiving status again.

![alt text](image.png)

### Step 2: Alert log file

- Identify the location of the alert log file.

![alt text](image-1.png)

![alt text](image-2.png)

### Step 3: Monitor the alert log

- Shutdown "SADB" with the most safe and fast method. and monitor the alert log

```
 tail -100  /u01/app/oracle/diag/rdbms/sadb/SADB/alert/log.xml

```
![alt text](image-9.png)

### Step 4: 

- Startup "SADB" step by step. and monitor the alert log

![alt text](image-4.png)

#### at startup nomount 

![alt text](image-10.png)

#### at alter database mount

![alt text](image-11.png)

#### at alter database open:

![alt text](image-12.png)

### Step 5: Create a user

- Create user "myuser" and make "iti_data" tablespace his default tablespace with unlimited quota on it.

![alt text](image-5.png)

### Step 6: Connection trials

- try to connect with the new created user.

![alt text](image-6.png)

### Step 7: Giving user privilges

- give the new user connect, resource and create view privilges.

![alt text](image-7.png)

### Step 8: Monitor the alert log again

- shutdown "SADB" with the most safe and fast method. and monitor the alert log

![alt text](image-8.png)

### Step 9: Unlock the hr user if locked.

![alt text](image-13.png)

As far as i can remember, we didn't install the hr schema while installation.


- checking status of myuser:

![alt text](image-14.png)

### Step 10: Create ROLE

- create role "myrole" including "create session" privelege, create view.
 --> to know what privileges in a role, query on dba_sys_privs view.

![alt text](image-15.png)

### Step 11: Create PROFILE

- create profile "myprofile" which restrict the password age of the user to be 5 days, number of failed logins to three times and restrict its connect time. 

![alt text](image-16.png)

### Step 12:

- create an OS user with name "iti" and make him login to the database using "sqlplus /"

![alt text](image-17.png)

![alt text](image-18.png)

### Step 13:

- make your personal Operating system user to connect locally without authentication as sysdba.

#### solution was to add iti to dba group

![alt text](image-19.png)

![alt text](image-20.png)

### Step 14:

- grant sysdba privlige to your created user "myuser" and then show all users that have sysdba privilige.

![alt text](image-21.png)

![alt text](image-22.png)
