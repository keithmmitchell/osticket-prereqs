<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Create a virtual machine
- Item 2
- Item 3
- Item 4
- Item 5

<h2>Installation Steps</h2>

In Azure create a resource group by clicking on Resource Groups in the top menu then click on create.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/3e5c2e53-db25-4ab6-9b8a-85724d311280)

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/721edf3b-629e-49c4-9826-7c542eda46b2)

For the Resource Group I named it RG-osTicket and selected te region (Europe) UK South then Review and Create.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/db065d8b-e332-4151-859e-91d692f96816)

Search Virtual Machines in the search bar and create a new Virtual Machine.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/ba9fe64a-c8ff-41d7-abfe-7f53d8684f31)

I used the following configuration:

- Resource Group: RG-osTicket
- Virtual Machine Name: vm-osticket
- Region: (Europe) UK South
- Image: Windows 10 Pro
- Size: Standard_D4s_v3 - 4vcpus, 16GiB memory
- Username: labuser
- Password: Passw0rd1234

Check the box to confirm licensing.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/167f3f28-b467-4ce1-8ce7-6a02bc4ebd6d)

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/11f71b8b-2106-4df1-aa72-7875a7bb376c)

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/c623bf05-42ad-4330-9403-5a68261470bb)

Click Next to Disks then Next again to Networking.  All the defaults look good so click Review and Create.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/cdfb9b5a-865f-438f-9d7a-76b2d4ade431)

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/bac234ed-7010-4cc5-b194-a5e5a5bb4dfe)

After a short while the deployment is complete.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/f59db7c2-98f1-4d9e-a394-35a34048e220)










