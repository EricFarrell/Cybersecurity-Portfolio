## Greenbone Vulnerability Manager
### Objectives
- Check if Greenbone was setup properly
- Update Greenbone
- Setup Snort
- Run scans on pfSense with Snort enabled


### Greenbone check Setup
The gvm-check-setup command in Kali Linux is used to check if the Greenbone Vulnerability Manager (GVM) has been set up correctly. It verifies that all necessary components, such as services, configurations, and vulnerability data, are installed and running properly. If there are issues, it provides helpful messages to guide you in fixing them.

<img width="1128" alt="GVM" src="https://github.com/user-attachments/assets/c8d0ef08-c310-4d09-a2a6-d8764ad600b3" />

### GVM Start
The gvm-start command in Kali Linux is used to start all the necessary services for the Greenbone Vulnerability Manager (GVM). It automatically opens a new browser and takes you to the web interface.
![greenbone main](https://github.com/user-attachments/assets/4d3f7f4a-468b-4ecf-9fc7-bcd2b37a2ada)


### GVM Scans
Within GVM, I created a new scan and inputted the IP address of the pfsense VM after all configurations were completed on pfSense. I named this scan "Snort".
![image](https://github.com/user-attachments/assets/858bc06a-2890-48cd-a28e-645566cf1515)

The next two photos are the results of the scan. GVM detected that the default credentials were still being used on pfSense. Along with an outdated or end of life scan engine. Ways to prevent these are by creating secure login credentials that are not easily guessed. And updating software so there won’t be any loss of functionality, bugs, or incompatibilities.
Hardening can enhance the ability to detect during network scans due it its ability to have custom rules. There can be filters applied where when a certain type of connection is made, it will filter and show only those results. There are also alerts that can provide a better view of scanning activities while minimizing false positives. 


![image](https://github.com/user-attachments/assets/fc4a47c6-a6f8-42fa-8ea5-9e732d825028)
![image](https://github.com/user-attachments/assets/ae03dfb9-31d1-40b7-b0fb-2ac13eaf261b)


