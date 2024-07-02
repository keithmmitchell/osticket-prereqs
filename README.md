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

Click on Go To Resource and copy the public IP address.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/0cc8a08b-1c80-46da-a00e-769e96a4dd66)

On the physical PC search Remote Desktop for Remote Desktop Connection and paste the IP address and click Connect.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/ef4b3cb4-e0f1-4d92-959d-a79c872dfc13)

Enter the username labuser and the password Passw0rd and click OK to connect.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/6638c862-ad28-4f1a-984c-774cceb9add8)

Click Yes when the message appears about the identity not being identified.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/81a97c58-dc17-4045-a024-ffbe771a310a)

On  the vm-osticket machine select Yes to make the PC discoverable on the netweork.

Next, IIS needs to be enabled on the machine so right click the Start menu and select Run. Type "Control" then Enter to bring up the Control Panel and then select Programs.   

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/eaaf88d1-d731-4509-a2b3-4aa85ef9661c)

Click Turn Windows features on or off

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/49a65b75-ffce-44dd-8323-a01031dcb96a)

In the list expand Internet Information Services and World Wide Services and Application Development Features then select the CGI checkbox.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/82f76b71-306f-49cb-b235-c5b7bcf91878)

Then go to HTTP features and make sure that all checkboxes are selected then click OK.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/955db9ad-2551-4fce-b554-527ba57d3051)

Next we need to confirm the web server is installed before we carry on with the rest of the steps.

Open Edge and type the local host 127.0.0.1 and if the Internet Information Services screen appears then it's working.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/2a03bfbd-465c-40e0-82f7-7ab2e39f7e8c)

THe next step is to install PHPManager for IIS from https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6.

<br />

Download the PHPManagerForIIS file and install it.

<br/>

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/82135c4b-2891-42dd-8c7b-2981148bc7ee)

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/1b228f58-6856-4cc4-a4b2-baca9bc23ffd)

Once installed click Close.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/bd157304-fda5-4171-bf6a-68359c9607fe)

Next, download the rewrite module.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/25c782f0-4404-406c-9900-6994c7a958d5)

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/c3832a1c-8d84-46c9-b9d7-03cfdf9c6421)

Click Finish once installed.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/6c94f61f-b58a-4017-960e-471594c76983)

Next, the directory C:\PHP needs to be created.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/2d11b75a-a469-4aa2-8cd1-a2fec63ee7d3)

Next, download the PHP7.3.8 zip file and extract to the PHP folder by right clicking the zip file and select Extract All.  Browse for the c:\PHP folder and click Extract and the folders and files will extract to the drive.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/b2aa4b1a-b13e-456f-a41f-0da6d320f63e)

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/a38a8617-27ce-4a6c-b77b-e3bce05b0450)

Next, download the VC_redist file and install it.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/896bb028-5fe6-487c-9575-681a854bfe56)

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/f48922d6-e841-4376-ae1a-ace04da77bf1)

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/b5ff6e0d-bafd-4b03-a931-7a181823a84b)

Next, download and install MySQL server.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/5ad60eff-6a2c-4ffe-bccd-6471e0ce2c85)

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/292b7d5a-741f-4e84-8f15-9ad711611551)

For setup type choose Typical.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/e7eb5617-a4a0-4355-bc4c-7b19b03440e8)

Make sure the MySQL Instance Configuration Wizard is checked and click Finish.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/e8c64ec7-7a9e-43cf-b93b-e474e8922854)

In the Configuration Wizard click Next.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/fa1f3635-509a-43cd-bbd5-187e9411e41a)

Choose Standard Configuration.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/b3f4b22a-6188-4e08-8e4f-6701c72b8d4d)

Then click Next.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/bc1a3cc7-c7a3-4a7e-b2e7-ef0dc9d6e3a4)

On the following screen use the password Password1.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/10a1f131-2b3d-45d1-a65b-ac2e72dde399)

Then click Execute.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/67d2b370-ebca-41e3-b0d4-9836d462d3f0)

Next, search IIS, right click and run as Administrator.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/5f6f1de8-76c0-4cf3-992b-0b2bddf9c836)








