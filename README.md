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

You can use terminal from proxmoxve to operate or you can use external application like putty

you can confirm your debian and proxmox version as shown below

![image](https://user-images.githubusercontent.com/76242298/136338524-9ae5b946-f9a6-4bca-bcec-bbf0eecaa1de.png)

## Creating virtual machine
### Add the iso file to proxmox first

![image](https://user-images.githubusercontent.com/76242298/136353533-31d58f62-e6dd-497c-bcfd-3153664e7bf3.png)

Now we can create a vm by clicking the button

![image](https://user-images.githubusercontent.com/76242298/136353277-a006a8a1-bbfa-4882-bf4f-9de7524e84fd.png)

configure the vm 

![image](https://user-images.githubusercontent.com/76242298/136353691-710a825b-ff07-4377-b306-ad6e9c53d9da.png)

Summary of vm we created 

![image](https://user-images.githubusercontent.com/76242298/136354050-5fcd9c52-85a0-442d-b2ad-b05dce5d131f.png)

In bottom section we can see the task that is done

![image](https://user-images.githubusercontent.com/76242298/136354224-8b1f6867-b012-4b08-81eb-023a2e67dbaf.png)

Here i have use lubuntu a very light weight linux os 

![image](https://user-images.githubusercontent.com/76242298/136355908-c67ec580-fcc9-4043-a741-b28e83614841.png)

Below is the image of options you can play around of a vm

Since our server is ruuning on vm kvm hardware virtualization is not set. But if it was a physical server than it should be enabled

![image](https://user-images.githubusercontent.com/76242298/136358031-6767b777-e9d4-4f9e-877f-9b508829a306.png)

## Containers

Before creating container we should first download template

![image](https://user-images.githubusercontent.com/76242298/136500396-ea36d805-a252-463f-bde6-25d80a74f0dc.png)

Download any template,I will go with centos default 8

![image](https://user-images.githubusercontent.com/76242298/136500667-0cd11f2b-6427-4b54-a1cd-e21d07e75627.png)

Now create container by clicking on top right corner and configure it

![image](https://user-images.githubusercontent.com/76242298/136501841-5f1d34f5-1379-492e-9db3-e8b5dcf26989.png)

![image](https://user-images.githubusercontent.com/76242298/136502131-53b7fc85-1c3a-428b-91c9-0a99b792a241.png)

Now it should be working

![image](https://user-images.githubusercontent.com/76242298/136502282-a938db1e-8fb2-4af4-9c3b-f758c92ee08b.png)

Now containers can be controlled from host kernel itself , Here I am executing command from host shell

![image](https://user-images.githubusercontent.com/76242298/136502514-e5e94f9d-d6ae-4198-b478-e8f82a7aae04.png)

## Advanced Memory Configuration

In Proxmox it has a feature to set minium memory for a given Virtual machine or any container as a whole. This enables us to implement Ballooning concept

Basically we can allocate  memory to all the virtual machine which total would be greater than the underlying hardware capabality. This is possible because the underlying hypervisor in our case Proxmox will make sure to allocate memory dynamically at a given time based on the need of individual machine . But since we can allocate minimum memory 
it make sures minimum memory is always allocated and there is no starvation as shown in below image.

![image](https://user-images.githubusercontent.com/76242298/139872600-bf45cf35-c8f7-4ce3-906d-f67a98a1a907.png)


## Network Configuration

### Creating a Bond interface
We can create any type of network configuration by clicking on create first 
![image](https://user-images.githubusercontent.com/76242298/139873721-288bd700-b9d5-47f3-8445-006d938c9d2c.png)

Now if I try pinging the ip addrress of bond and in the middle if I disconnect one network adapter the other network adapter should be able to take car of it 

![image](https://user-images.githubusercontent.com/76242298/139875701-e431de71-98b5-478f-94c6-bb42beac64ad.png)

In the above snapshot there is only 1 time when there is request timed out but after that it once agains starts pinging









