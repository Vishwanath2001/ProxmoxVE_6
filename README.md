# ProxmoxVE_6
College project to create and maintain a fully virtualized Data Center 

19BCE1499,
19BCE1448,
19BCE1302,
19BCE1521

##### project is still under development and not finsihed

## Download Vmware 
We are going to install proxmox on vmware workstation but even VirtualBox can also be used
Vmware can be downloaded from here:- https://www.vmware.com/products/workstation-player.html

Once it is downloaded go ahead and install it

![image](https://user-images.githubusercontent.com/76242298/134470980-40ebc1a4-57a2-4201-8c1b-6298387a0149.png)

Accept the agreement

![image](https://user-images.githubusercontent.com/76242298/134471178-4226b213-c5c8-4712-abb9-74e68a3aac84.png)

 Install it
 
 Make sure to select "add vmware to system path" checkbox
 
![image](https://user-images.githubusercontent.com/76242298/134471229-5c4ce1d1-3183-4131-a1a9-a461bb6f2f10.png)

## Installing proxmoxVE

Before proceeding make sure your system virtualization is enabled in bios ,Both intel and amd suports virtualization

Use this as for reference to enable virtualization:- https://www.sony.co.in/electronics/support/articles/S500016173

### Download ProxmoxVE

proxmoxVE is a open source and free to use for personal use and they have many subscriptions and benifits for this project we are going to make use of free version

Download it from here:
https://www.proxmox.com/en/proxmox-ve

It is pretty straight forward installation but there are certain tweeks we need to make
![image](https://user-images.githubusercontent.com/76242298/136316987-72bda7e2-f888-40f3-94fa-656b705db814.png)

Make sure to check all the 3 checkboxes as shown below

![image](https://user-images.githubusercontent.com/76242298/136317223-625cd7f1-7ca2-4f26-8d1f-8b202b2048ff.png)

Under Network Adapter select bridged so vm can connect to host network

![image](https://user-images.githubusercontent.com/76242298/136317360-98b5b1fb-cfee-4788-a163-7b0e047ac576.png)

Now start the vm

![image](https://user-images.githubusercontent.com/76242298/136317533-828aef0f-e1fa-42f1-b044-fe0ca6dd8ae9.png)

Give hostname of your choice and ip address as shown below

![image](https://user-images.githubusercontent.com/76242298/136317780-8c5e00a9-e909-482f-83eb-92060b309626.png)

After confirming the configuration go ahead and install it

![image](https://user-images.githubusercontent.com/76242298/136317941-7323ae85-56f7-4dc8-89dc-9f40b720c1e9.png)

Now the ip address which you gave during installation should be used to use web interface of proxmoxve

Proxmox will give you the address

![image](https://user-images.githubusercontent.com/76242298/136337319-31f10f10-2475-4155-a6d0-51e6e01f04b5.png)

If you visit that address you will get below interface

![image](https://user-images.githubusercontent.com/76242298/136337406-63de4427-8d5c-4bf2-976e-a2ace1da8282.png)

root is username and password which you gave during installation

Once you login this is how your inteface will look like

![image](https://user-images.githubusercontent.com/76242298/136337541-d14c91bd-21af-4591-bfe4-43da61691f8e.png)





