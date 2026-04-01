# Azure Virtual Network Setup Lab 💻🛜🖥️

This lab demonstrates how to build a basic cloud environment using Microsoft Azure.
The goal is to simulate a small IT infrastructure that a help desk or junior system administrator might support.

## Lab Objectives
Create and organize resources using Resource Groups

Configure a Virtual Network for cloud connectivity

Deploy 2 Virtual Machines

Verify the environment is working correctly

---

## Enviornments Used 

Microsoft Azure 
Microsoft Windows 10 Enterprise, version 22H2 - x64 Gen2
Remote Desktop Connection (RDP)
Windows Command Prompt (CMD)


### Step 1: Create a Resource Group

A Resource Group helps organize and manage all related resources in Azure.

1. Sign in to the Azure Portal
2. Go to Resource Groups
3. Click Create
4. Configure:
- Subscription: Your Azure subscription

- Resource Group Name: TensLabs
- Region: Choose a nearby region
   - Canada Central 
5. Click Review + Create
6. Click Create

<img width="281" height="137" alt="resourcegroupcreation" src="https://github.com/user-attachments/assets/02d8776b-db81-454b-ab02-117e3e822460" />

Resource Group successfully created.

---

### Step 2: Create a Virtual Network

Next, I created a Virtual Network (VN) to allow resources, my two virtual machines, to communicate.

1. Go to Virtual Networks
2. Click Create
3. Configure the following:


Resource Group: TensLabs
  - Virtual Network Name: Teni-VNet

Region: Same region as the resource group
  - Canada Central 
   
IP Addressing

  - Address Space: 10.0.0.0/16

4. Click Review + Create
5. Click Create

<img width="845" height="377" alt="vnoverview" src="https://github.com/user-attachments/assets/fed36855-e48e-4b67-ac5b-98397fd12cde" />

Virtual Network overview page.

---

### Step 3: Deploy Virtual Machines

Create a virtual machine that will act as a workstation or server.


1. Go to Virtual Machines
    - Click Create → Azure Virtual Machine

2. Configure:


- Resource Group: TensLabs
- Virtual Network: Teni-VNet 
- Virtual Machine Name: Windows10VM

- Region: Canada Central 

- Image: Windows 10 Enterprise

- Size: Standard D2s v3 (2 vcpus, 8 GiB memory)




**Administrator Account** 

 Create Username and Password

 - Username: Admin10




<img width="477" height="256" alt="deploymentvm" src="https://github.com/user-attachments/assets/1a2afc2a-c4fe-4662-9ae6-3c4e71518e06" />
<img width="491" height="334" alt="vmdeployed" src="https://github.com/user-attachments/assets/a49f043f-13a8-4297-be47-bd767e580901" />

VM deployment in progress.



### Create a second virtual machine that will act as another user on the network. 

Configure: 
- Resource Group: TensLabs
- Virtual Network: Teni-VNet 
- Virtual Machine Name: LinuxVM

- Region: Canada Central 

- Image: Linux (ubuntu 24.04)

- Size: Standard D2s v3 (2 vcpus, 8 GiB memory)


<b>User Account</b> 

  Create Username and Password 

  - Username: Linuxuser

<img width="232" height="98" alt="Linuxdeploymentcomplete" src="https://github.com/user-attachments/assets/384e097a-82dc-472d-b9ce-6d32b4fda21c" />
<img width="532" height="311" alt="linuxvmdeployed" src="https://github.com/user-attachments/assets/353443d4-f873-450e-b62f-84be001ae0db" />


---

### Step 4: Connect to the Virtual Machine

Once deployment was complete, I tested connectivity using Windows Remote Desktop Connection.

1. Open the Virtual Machine
2. Click Connect
3. Select RDP
4. Download the RDP file
5. Open the file and log in using:
  - Username: Admin10
  - Password: (your password)

This confirms the VM is working properly.

<img width="951" height="500" alt="windowsvmconnection" src="https://github.com/user-attachments/assets/7193c40b-581d-49a2-a94b-11bea9354be6" />


Remote Desktop connected to the VM.


<b>Verify connection of LinuxVM using Powershell</b>

1. Opened PowerShell 

Run:

  - ssh <Linuxuser>@<130.107.145.240>

    Secure Shell (SSH) works and VM is visible from my computer. 
<img width="599" height="282" alt="linuxpowershell1" src="https://github.com/user-attachments/assets/dc7c517a-4bbf-498b-8fb6-021fc0651359" />

<img width="588" height="71" alt="linuxinpowershell" src="https://github.com/user-attachments/assets/9b3d57d8-da17-4d83-98c7-d63ef93095a7" />


### Step 5: Verify Network Configuration

Inside the VM, I confirmed network connectivity.

1. Open Command Prompt
Run:
ipconfig

Checked for IP address from the subnet:

10.0.0.4

This confirms the Virtual Network is configured correctly.

<img width="494" height="272" alt="network connected " src="https://github.com/user-attachments/assets/1cffbba9-3403-4418-aa2c-a36245848122" />

Command Prompt showing the VM IP address.

## What I Learned 

I verified communication between systems using tools like RDP and SSH and observed how different operating systems handle remote access. I learned that Windows VMs are easier to connect to with a graphical interface by default, while Linux typically requires SSH and additional configuration (such as installing xRDP and a desktop environment) to enable GUI access. This exercise helped me better understand Azure networking, inbound port rules, and real-world troubleshooting when remote connections do not work as expected.
