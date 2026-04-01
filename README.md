# Azure Virtual Network Setup Lab

This lab demonstrates how to build a basic cloud environment using Microsoft Azure.
The goal is to simulate a small IT infrastructure that a help desk or junior system administrator might support.

## Lab Objectives
Create and organize resources using Resource Groups

Configure a Virtual Network for cloud connectivity

Deploy 2 Virtual Machines

Verify the environment is working correctly

---

### Step 1: Create a Resource Group

A Resource Group helps organize and manage all related resources in Azure.

1. Sign in to the Azure Portal
2. Go to Resource Groups
3. Click Create
4. Configure:
Subscription: Your Azure subscription

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
Virtual Network Name: Teni-VNet

Region: Same region as the resource group
  - Canada Central 
   

IP Addressing

Address Space: 10.0.0.0/16

Subnet

Subnet Name: IT-Subnet
Subnet Range: 10.0.1.0/24
Click Review + Create
Click Create

<img width="845" height="377" alt="vnoverview" src="https://github.com/user-attachments/assets/fed36855-e48e-4b67-ac5b-98397fd12cde" />

Virtual Network overview page.

---

### Step 3: Deploy a Virtual Machine

Now we create a virtual machine that will act as a workstation or server.

Search for Virtual Machines
Click Create → Azure Virtual Machine

Configure:

Basics

Resource Group: IT-Support-Lab
Virtual Machine Name: IT-Lab-VM
Region: Same as previous steps
Image: Windows 10 or Windows Server
Size: Choose a free-tier eligible size if available

Administrator Account

Username: labadmin
Password: Create a secure password

Networking

Virtual Network: IT-Lab-VNet
Subnet: IT-Subnet
Public IP: Enabled
Click Review + Create
Click Create

📸 Screenshot suggestion:
VM deployment in progress.


---

### Step 4: Connect to the Virtual Machine

Once deployment is complete, we test connectivity.

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
