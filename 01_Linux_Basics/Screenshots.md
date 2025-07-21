# Step 1: Identity & System Info

1.   whoami          

2.   id             

3.   hostname      

4.   uname -a        

5.   cat /etc/os-release   



![Week 1 Step 1](https://github.com/user-attachments/assets/f3a9131c-1176-40c3-829e-29fcd759793a)

## Output of `Step 1 commands`.
__________________________________________________________________________________________________________

# Step 2: User Enumeration

1.   cat /etc/passwd

2. cut -d: -f1 /etc/passwd

3. getent passwd



![Week 1 step 2 (1)](https://github.com/user-attachments/assets/a12b5330-02bf-4916-bcb9-9a882221c5c8)

![Week 1 step 2 (2)](https://github.com/user-attachments/assets/3d8907be-9c07-43b9-824f-17a634906a42)

![Week 1 step 2 (3)](https://github.com/user-attachments/assets/b2de60f3-331b-4d5f-8978-04f48774edc4)

## Output of `Step 2 commands`.
__________________________________________________________________________________________________________

# Step 3: Group Membership & Sudo Access

1. groups       

2. sudo -l     


![Week 1 step 3](https://github.com/user-attachments/assets/a6b7557a-3576-4fa8-95d0-cadd1f7559ba)

## Output of `Step 3 commands`.
__________________________________________________________________________________________________________

# Step 4: Find SUID Binaries

1. find / -perm -4000 -type f 2>/dev/null


![step 4](https://github.com/user-attachments/assets/8bdecc55-7a11-4f5f-92dd-469665c42dd3)

## Output of `Step 4 commands`.
__________________________________________________________________________________________________________

# Step 5: Writable Folders & Files

1. find / -writable -type d 2>/dev/null   

2. find / -name "*.sh" 2>/dev/null        


![step 5 (1)](https://github.com/user-attachments/assets/e9070373-0a19-4b4b-8170-d4a253f163ca)

![step 5 (2)](https://github.com/user-attachments/assets/8af79110-4ca4-4585-a344-410094917d39)

## Output of `Step 5 commands`.
__________________________________________________________________________________________________________

# Step 6: Check for Cron Jobs

1. cat /etc/crontab

2. ls -la /etc/cron*

3. ps aux | grep cron


![step 6 (1)](https://github.com/user-attachments/assets/8c530bf1-9008-440e-a297-d2d14c00cbb3)

![step 6 (2)](https://github.com/user-attachments/assets/7035b0b0-2c29-43aa-b932-6adde0549713)

![step 6 (3)](https://github.com/user-attachments/assets/27717af3-01fa-470a-9a19-15e8c689ad62)

## Output of `Step 6 commands`.

__________________________________________________________________________________________________________

# Step 7: Use linPEAS for Automation

- wget https://github.com/carlospolop/PEASS-ng/releases/latest/download/linpeas.sh

- chmod +x linpeas.sh

- ./linpeas.sh

![step 7 (1)](https://github.com/user-attachments/assets/ddaf4f4c-17ee-4782-b653-e0d7b6d23261)

![step 7 (2)](https://github.com/user-attachments/assets/80e191b9-3700-4996-9914-0faa8a8fa9b7)

![step 7 (3)](https://github.com/user-attachments/assets/934099f0-1fd6-4ce2-bc6b-c52c8408598d)

![step 7 (4)](https://github.com/user-attachments/assets/f2612cb4-8639-44d8-bfdc-a3b9d72489e0)

![step 7 (5)](https://github.com/user-attachments/assets/0a6cff09-ee23-4afa-9412-04a9ce157d54)

## Output of `Step 6 commands`.
__________________________________________________________________________________________________________



















