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































