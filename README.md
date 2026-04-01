# Azure Virtual Network Setup Lab

This lab demonstrates how to build a basic cloud environment using Microsoft Azure.
The goal is to simulate a small IT infrastructure that a help desk or junior system administrator might support.

## Lab Objectives
Create and organize resources using Resource Groups

Configure a Virtual Network for cloud connectivity

Deploy 2 Virtual Machines

Verify the environment is working correctly

---

## Enviornments Used 

Microsoft Windows 10 Enterprise, version 22H2 - x64 Gen2
Ubuntu 


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

Once deployment is complete I tested connectivity using Windows Remote Desktop Connection.

Open the Virtual Machine
Click Connect
Select RDP
Download the RDP file
Open the file and log in using:
Username: labadmin
Password: (your password)

This confirms the VM is working properly.

📸 Screenshot suggestion (Important):
Remote Desktop connected to the VM.

This is the screenshot that proves the lab worked.

Step 5: Verify Network Configuration

Inside the VM, confirm network connectivity.

Open Command Prompt
Run:
ipconfig

You should see an IP address from the subnet:

10.0.1.x

This confirms the Virtual Network is configured correctly.

📸 Screenshot suggestion:
Command Prompt showing the VM IP address.

## Lab Results

In this lab I successfully:

Built a cloud environment
Configured Azure networking
Deployed and connected to a virtual machine
Verified connectivity inside the VM

This simulates tasks commonly performed by IT support technicians working in cloud environments.

## Skills Demonstrated

Cloud Administration
Virtual Networking
VM Deployment
Remote Desktop Troubleshooting
Azure Resource Management
