<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- IIS
- PHP Manager
- Rewrite Module
- VC_redistx86
- MySQL 5.5.62
- Heidi SQL

<h2>Installation Steps</h2>

In Azure create a resource group by clicking on Resource Groups in the top menu then click on create.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/4e12b849-570d-4d3d-a53e-2719cc12b134)


<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/721edf3b-629e-49c4-9826-7c542eda46b2)

For the Resource Group, I named it RG-osTicket and selected the region (Europe) UK South then Review and Create.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/db065d8b-e332-4151-859e-91d692f96816)

Search Virtual Machines in the search bar and create a new Virtual Machine.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/f3cc5794-6ae0-4a33-b6c1-a486d4cbe5e5)

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

Enter the username labuser and the password Passw0rd1234 and click OK to connect.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/6638c862-ad28-4f1a-984c-774cceb9add8)

Click Yes when the message appears about the identity not being verified.

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

The next step is to install PHPManager for IIS from https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6.

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

Next, search IIS, right click and run as Administrator and IIS Manager will load.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/5f6f1de8-76c0-4cf3-992b-0b2bddf9c836)

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/77c5a4fd-37a8-4d66-b6e3-4e6e00324d84)

Double click PHP Manager

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/5b098a74-f14a-423a-89ff-76593a6115d7)

We can see PHP is not enabled so click Register new PHP version.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/f7d4ff9c-b0f0-468e-9f44-4b974a03258b)

Browse to C:\PHP\php-cgi.exe and click OK.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/ff8e86d2-89c1-4c17-8b56-ca92ce4fac82)

Restart the server by clicking on the name then click Restart.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/d7f19276-9ae2-4348-92c5-603c20f8eed6)

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/02923a3b-3046-4c58-9316-2ef993517dbf)

Download osTicket from the installation files.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/bb2f90e2-7067-4fd8-8676-7066a0293589)

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/9d13504e-f2d1-4097-925c-a280675f65cf)

Now need to copy the "upload" folder to c:\inetpub\wwwroot.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/206787f2-901a-4688-9b47-4843f864831f)

Now rename the upload folder to osTicket.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/55894a3f-3be5-471d-97bb-f09039d9336b)

Restart IIS Manager again.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/919b7080-f221-49ab-b92b-5d0291728731)

Next go to Sites>Default Web Site>osTicket

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/20abe822-b427-4982-8f12-3a93c5450810)

Then on the right go to Browse*:80 (http) to bring up the osTicket installer in Edge.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/c123e112-75ed-42cc-8d31-662bf78df17d)

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/613c9102-efb6-4044-80c0-990b0fdda67d)

We can see that some of the extensions are not enabled so that needs to be done next.

Back in IIS Manager double click PHP Manager.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/a56f16a7-114a-4f9b-8c02-e7b417fb3713)

Click on enable or disable an extension then enable the following:

- php_imap.dll
- php_intl.dll
- php_opcache.dll

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/95b1fa2f-2e84-49f6-84ca-018b900e679f)

Back in Edge browser refresh to see those the extensions enabled.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/ccd4ce9d-37cb-4648-902e-8d35cf65374a)

<br />

Next is to rename the ost-config.php file from c:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php to c:\inetpub\wwwroot\osTicket\include\ost-config.php.

<br /> 

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/6a66df46-8374-48ed-8f7c-48a78ed5714a)

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/b4c78f85-7c01-4b05-8930-a7852a0b0b3b)

Permissions need to be assigned to the ost-config.php file so the osTicket installer can manipulate and interact with the file.  So right click the file and select Properties.  In the Security tab click Advanced.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/ad1dc287-0053-44a3-980f-701a854720be)

In the Advanced window select Disable Inheritance to stop it inheriting from it's parent.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/ebc1c633-d086-41a0-92e6-5cbdf6d19d04)

Then select Remove All Permissions.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/99c93032-c9e8-4191-8213-25f48803571d)

Once all the permissions are removed select Add.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/5c957d01-7be5-4e1d-af85-2698e4697f0c)

Click Select A Principal

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/44ee9739-7827-4ee2-80b0-7552143d499f)

Enter everyone then click Check Names then OK.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/2645c95c-2ead-4125-81d5-3edfb17610ed)

Then give everyone Full Control and click OK.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/2384717f-acf1-4020-aa58-0a52241a5036)

Click Apply and OK then OK again.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/72af035a-7ac1-45bf-8a8e-e48915f6fd52)

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/64df0c08-ac54-457a-985e-123acbba4925)

Continue setting up osTicket in Edge by clicking Continue.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/8284d93e-ca9e-44e2-b32d-89e9a09fb0c4)

Enter the following details:

- Helpdesk Name:  Keith Helpdesk
- Default Email: keith@helper.com
- First Name: Keith
- Last Name: Mitchell
- Email: Kmmitch79@outlook.com
- Username:   
- Password: Passw0rd

Next HeidiSQL needs to be installed to set up the SQL database.  Back in the Installations tab in Edge download HeidiSQL.

<br/>

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/c11fb077-ea9a-46f9-9a51-90735596809d)

<br />
::
![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/fbf76f8b-da70-4a19-a7e2-5f886b6d8e76)

Work your way through the installation by accepting the licensing agreement then clicking Next everytime then Install and then Finish to launch HeidiSQL.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/8cd59fe2-7dce-406c-84d0-40b06ce630fa)

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/1572b50a-d170-448a-b662-04750ed0838d)

In HeidiSQL click New on the bottom left corner to create a connection to the database.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/8c8a8994-f64b-4843-af31-9fc909ee8ed4)

Enter the password Password1 then click Open.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/844e2c0c-13c3-4d07-91c3-f7c48baf3184)

We now have Heidi connected to the database.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/97f98920-d613-44d0-a476-ad86c24a7041)

Back in Edge enter the following:

- MySQL Username: root
- MySQL Password: Password1

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/40fb0c07-50e9-4f82-99be-b7da1a0c8e64)

A new database needs to be created in Heidi called osTicket.  

In Heidi right click Unamed>Create New>Database.

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/70d29044-8b5c-4083-a8eb-c7f5cdfed710)

Enter the name osTicket and click OK.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/4b6c04f5-e448-442d-8583-fd76e0ee5837)

We can now see it created.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/2be583fb-3648-4fa9-a378-6ac8d81d0ff7)

Back in Edge enter osTicket for MySQL Database then click Install Now.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/f4750cb8-0a22-49e1-aae8-b23424fc84a9)

Now need to do some clean up.  The folder c:\inetpub\wwwroot\osTicket\setup needs to be deleted.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/bbf4b42c-0745-451f-ade9-2abc1a666608)

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/d63c0ee1-b4fa-4f35-b260-f14e0a783adb)

Next the file c:\inetpub\wwwroot\osTicket\include\ost-config.php needs to be set back to to Read Only.  To do this right click the file and select Properties then the Security tab.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/4095efbf-4c81-41d1-b193-a75a697495e7)

Click Advanced then select Everyone and then Edit.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/98b304be-7393-475b-ac05-e4e69ce41f89)

Make sure the only permissions checked are Read and Read & Execute then click OK.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/d68ff004-ef61-4db4-b079-9185902e49b8)

Then Apply and OK.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/ecb66213-3558-47ab-b182-625ff3993791)

And then OK again.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/e9178f93-ba09-4d7c-9c08-7865aecb0bb1)

The URL for the login page is http://localhosts/osTicket/scp/login.php so go there and test that it's working.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/89151aae-d83e-4bf1-9156-fb312d9346ec)

Log in with the username user_admin and password Passw0rd.

<br />

![image](https://github.com/keithmmitchell/osticket-prereqs/assets/174253055/14378c50-1706-4af0-8fbc-5086cdc8ecd8)

<br />

That brings us to the end of Part 1 of the lab.  Please click https://github.com/keithmmitchell/post-install-config to go to Part 2.










