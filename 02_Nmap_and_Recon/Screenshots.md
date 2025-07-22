# Step 1: Discover Live Hosts: (Ping Sweep)

1. nmap -sn 192.168.1.0/24


![WhatsApp Image 2025-07-22 at 2 55 39 PM](https://github.com/user-attachments/assets/e90923c6-8306-47ff-bd7e-18f3fa108942)

## Output of Step 1 commands.

# Step 2: Scan Open Ports:

1. nmap -sS -p- 192.168.1.10

![WhatsApp Image 2025-07-22 at 3 10 54 PM](https://github.com/user-attachments/assets/5c5bd93d-a01e-4602-b9f4-b5c0bdb0a0c2)


## Output of Step 2 commands.

# Step 3: Service & Version Detection

1. nmap -sV 192.168.1.10

![WhatsApp Image 2025-07-22 at 3 21 58 PM](https://github.com/user-attachments/assets/68005256-1743-4e3f-90ce-51a7974b378d)

## Output of Step 3 commands.

# Step 4: OS Detection

1. nmap -O 192.168.1.10

![WhatsApp Image 2025-07-22 at 3 16 53 PM](https://github.com/user-attachments/assets/c77cee37-e9e5-4ac9-9563-f5f28f2a7ec5)

## Output of Step 4 commands.

# Step 5: Aggressive Scan: (All-in-One)

1. nmap -A 192.168.1.10

![WhatsApp Image 2025-07-22 at 3 35 33 PM](https://github.com/user-attachments/assets/362d46ba-5a98-4628-b623-24ebcc0ca8cd)

## Output of Step 5 commands.

# Step 6: Scan Specific Ports:

1. nmap -p 21,22,80,443 -sV 192.168.1.10

![WhatsApp Image 2025-07-22 at 3 37 34 PM](https://github.com/user-attachments/assets/4b0cd7ef-92d9-4362-a572-b3afad510faa)

## Output of Step 6 commands.

# Step 7: Run Nmap Scripts: (NSE)

1. nmap --script vuln 192.168.1.10
  
2. nmap --script http-enum 192.168.1.10

![WhatsApp Image 2025-07-22 at 3 40 48 PM](https://github.com/user-attachments/assets/95b531cf-d448-4b22-8f2c-10a49cb28711)

![WhatsApp Image 2025-07-22 at 3 43 50 PM](https://github.com/user-attachments/assets/c19d30b4-ddd0-4b6a-8a16-55d11a630cff)

## Output of Step 7 commands.

# Step 8: Save Scan Results:

1. nmap -sV -oN basic-scan.txt 192.168.1.10

![WhatsApp Image 2025-07-22 at 3 48 48 PM](https://github.com/user-attachments/assets/949482a2-9162-472d-8d03-6f1cd46ee641)

## Output of Step 8 commands.

# Step 9: Web Recon: (If Port 80/443 Found)

1. whatweb http://192.168.1.10

2. nikto -h http://192.168.1.10

![WhatsApp Image 2025-07-22 at 3 55 15 PM](https://github.com/user-attachments/assets/f3f4dcb4-e6f2-48e1-a468-be84e9c75007)

## Output of Step 9 commands.









