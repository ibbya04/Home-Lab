# Home Lab

## Objective

This Home Lab project aimed to create a controlled environment with virtual machines, for simulating and defending against cyber attacks. The focus was on using Kali Linux to launch attacks on an Ubuntu VM, while using UFW for defense and analyzing network traffic with Wireshark. This hands-on experience was designed to enhance my understanding of cybersecurity TTP's, attack methods, and effective defense strategies.

### Skills Learned

- Learnt how to set up, configure and manage virtual environments.
- Experience in penetration testing with Metasploit.
- Developed skills in network traffic analysis using Wireshark.
- Ability to implement and configure firewall defenses with UFW.
- Enhanced understanding of attack patterns and security vulnerabilities.
- Development of critical thinking and problem-solving skills in cybersecurity.

### Tools Used

- VMware to create and configure the virtual machines.
- Kali Linux, a penetration testing platform to launch an attack.
- Metasploit, a penetration testing framework used to exploit vulnerabilities and simulate attacks
- Wireshark, for capturing and examining network traffic.
- UFW, a firewall management tool on Ubuntu for configuring and enforcing security rules.

## Steps

I started by downloading the disc images for Ubuntu and Kali, then uploaded them into VMware.

<img width="1470" alt="Screenshot 2024-09-18 at 17 07 02" src="https://github.com/user-attachments/assets/fa00aec4-4849-4699-9e4c-855caf41671f">

Then I set up both systems and configured network, disc and other settings. 

Once both were up and running, I updated and upgraded both systems to make sure they up to date.

<img width="1033" alt="Screenshot 2024-09-19 at 10 56 36" src="https://github.com/user-attachments/assets/8a5d38d4-e713-4a74-9cc8-0816d0af971b">

I then installed wireshark, nmap and Metasploit on Kali.

<img width="832" alt="Screenshot 2024-09-19 at 11 55 57" src="https://github.com/user-attachments/assets/f1fa32d3-a9fa-4d49-9e5e-5ae9e2a7cd30">

Then Wireshark and UFW on Ubuntu, with `sudo apt install wireshark UFW`, and turned on UFW.

<img width="580" alt="Screenshot 2024-09-19 at 11 58 03" src="https://github.com/user-attachments/assets/9a969c81-0098-48cd-b02d-d20d50a6aa38">

I got the hostname of my Ubuntu machine, which I would target from Kali, and the hostname of my Kali machine and allowed that host on Ubuntu.

<img width="642" alt="Screenshot 2024-09-19 at 13 27 52" src="https://github.com/user-attachments/assets/139ef7df-1351-4891-b23d-4da464a3c46d">

I then started Wireshark on the Ubuntu machine with `sudo wireshark`, and ran an nmap scan from Kali to the target Ubuntu machine.

<img width="764" alt="Screenshot 2024-09-19 at 13 34 50" src="https://github.com/user-attachments/assets/19768475-0a42-466e-a9f8-b91808921f41">

<img width="1268" alt="Screenshot 2024-09-19 at 13 34 35" src="https://github.com/user-attachments/assets/9b9d85e8-a22b-4950-a8f0-ca92b7cb6306">

However the nmap scan showed no open ports on my Ubuntu VM, so I checked for open ports on Ubuntu.

<img width="926" alt="Screenshot 2024-09-19 at 14 03 54" src="https://github.com/user-attachments/assets/4391e4c6-3160-4634-8d7a-c4d7c4b2d1ab">

Some of these seemed to be open but the nmap scan couldnt see them. I then decided to start a service on my Ubuntu VM, so I installed apache2 web server and started that. I could now see this service listening on port 80, HTTP.

<img width="935" alt="Screenshot 2024-09-19 at 14 05 52" src="https://github.com/user-attachments/assets/276a6fe6-4445-4e8d-be85-59f1d0535633">

I then ran a nmap -sV scan, to get the version of services, which returned an open port, the apache web server.

<img width="767" alt="Screenshot 2024-09-19 at 14 09 56" src="https://github.com/user-attachments/assets/a9b2010c-86a4-40bf-be01-72b0117f6dd2">



## Using Metasploitable as a target machine

For Metasploitable, as it was for x86 architecture, I followed a tutorial to set it up on my macbook, which included coverting the .vmdk file to a .qcow2 (QEMU disk file), and then configured it in UTM 

