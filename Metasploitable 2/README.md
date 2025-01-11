## Metasploitable 2
### Objective
- Find exploit and prepare scanning tools (Nmap, Nikto, Nessus, & ZAP)

- Identify open ports, services, and versions

- Pinpoint known vulnerabilities, use Nmap, Nikto, Nessus, & ZAP

- Enable firewall within Metasploitable 2 and compare results

### NMap command
Nmap 192.168.56.0/24 to find IP address and open ports on Metasploit 2 VM.
![image](https://github.com/user-attachments/assets/73d8bcc6-24ba-4186-8aed-ec7b58923f5a)

### Nikto Scan
Nikto -h 192.168.56.104 for vulnerabilities found on port 80 (http)

#### Vulnerabilities Found
-Anti-clickjacking X-Frame-POptions header is not present

-Apache 2.2.8 is outdated

-Web Server returns valid response withjunk HTTP which can cause false positives
![image](https://github.com/user-attachments/assets/9301d841-4feb-414e-a88a-7a46407d5ab2)

## Nessus Basic Network Scan
Nessus found three critical vulnerabilities and one high vulnerability, with a total of 47 vulnerabilities. 
![image](https://github.com/user-attachments/assets/c8be1c23-3ddc-4c43-8932-037468d6a5b6)

### ZAP
ZAP scan gave many alerts
![image](https://github.com/user-attachments/assets/e5180682-b0ff-4f24-adc6-16f27647bbd2)

### Metaspolitable 2 VM 
First, I used the default login credentials to login. I noticed I didn't have root access, I then executed the command of "Sudo SU" to gain root access. I then did "VNC passwd" to change the password. "Ufw enable" to enable uncomplicated firewall. Once enabled, "UFW default deny" to block incoming connections to the system.

Since it's blocking all incoming traffic, I have to create a rule to allow legitimate connections. We can do this by "UFW allow ssh" and "UFW allow http"

![image](https://github.com/user-attachments/assets/9e87eba0-d115-48ff-ad36-96ae082f6f27)

## Nessus After Firewall enabled
After the firewall was enabled, I ran the same basic network scan and all but one critical vulnerablity were removed. Overall, there are now 21 vulnerabilities, compared to the 47 vulnerabilities before the firewall was enabled. 
![image](https://github.com/user-attachments/assets/45fba86c-2913-4e4b-9842-1012eb9cfc24)

