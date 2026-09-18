IT Project Building a Virtual Machine and Getting The RDP To work

This project is to demonstrate how to build a virtual machine and what to do if the ports on for connecting to the RDP are not working after being built.

What was needed for this project is a Auzre Virtual Machines,Azure Subscription, Windows 10 enterprise, Windows 10, and a can do attitude. 

Where this project will start is right after creating a resource group in Azure
<img width="1452" height="903" alt="Before everything went south" src="https://github.com/user-attachments/assets/65968428-6e73-461d-82bb-245bb3780fd2" />

When creating a virtual machine a few things are needed like Internet, Region , secuirty type, Image and size.
You may have to search around for the Image size that suits the computer best, My computer does not have windows 11. Going into the drop down selection menu for everything we will have to find The right Image.
 The selection of Windows 10 Enterprise version 22h2 - 64 Gen2 then under size I went and searched up where to find less memory as to take up less space. The size used was Standard_D2als_v7 - 2vcpus, 4 GiB memory just to shrink it down enough to run. The Next step was changing the security type to standard. Final Step in this was picking a region I chose central US.
 
<img width="1294" height="725" alt="Figuring out which Windows 10 could work with it" src="https://github.com/user-attachments/assets/86b675b0-0ebe-4154-a7c6-f86532afd65f" />

Now The next Step was Configuring the network. During this step Youll have to create a IPv4 Address space and a subnet
<img width="1913" height="912" alt="Before the subnet was added" src="https://github.com/user-attachments/assets/8851e641-78b8-4310-9ccf-c09db33abbc7" />

To create the Subnet you have to give it an IPv4 address space. 
<img width="1207" height="747" alt="Realizing had to add more thaen already did" src="https://github.com/user-attachments/assets/6d73244c-3470-489d-a003-fb95ab41d10f" />

Once added you will be given the ability to a add a subnet.
<img width="1383" height="814" alt="Adding in the subnet to get it work" src="https://github.com/user-attachments/assets/f948b83f-0061-4f79-a330-7350e747cd09" />

Now its working.finishing creating the VM and getting started on trying to get connected to it.
So you make the attempt to connect to your VM using RDP you can find the IP Address by going into the resource group and clicking on the Windows VM from there youll be able to find the VM.

<img width="1679" height="866" alt="The Virtual machine working" src="https://github.com/user-attachments/assets/3e712e5a-bcfc-493b-bc70-a4ab7e51328d" />
 
Type in RDP in your Windows search bar and click on it, this will be the image that pops up.

<img width="972" height="335" alt="Remote desktop connection before fail" src="https://github.com/user-attachments/assets/8371ca83-1d7b-4e08-813a-d913667820bf" />

Once this pops up if it works it will ask for a username and password to get in. which at this point thats what you want to see but if somethings wrong like a port you'll get an error like this.

<img width="606" height="275" alt="Port not working" src="https://github.com/user-attachments/assets/13237f33-ca5e-42f3-b080-79c7ce2090d9" />

Next you have to go into the network setting and whats going on. Once youre into network settings you can see what the problem is. The problem here was that port 3389 was denying access from the Soures IP(s)

<img width="1677" height="685" alt="Troubleshooting how to get the Port to open to be able to use without IP" src="https://github.com/user-attachments/assets/85529fee-15bd-4c13-ba84-e2120aac2a8c" />

To fix this create a port rule.
<img width="1856" height="883" alt="lab picutre trouble shooting ports" src="https://github.com/user-attachments/assets/a93bb873-f018-49a9-9ac4-bf4aba58b72a" />
Next step is setting up Destination port ranges, protocal, action.
When setting up the port ranges in the port rule you have to set a specific port for yours to work there are several but for this I chose TCP 8080 because the Ip was denying traffic to port 3389, Selected the TCP Protocal to make sure its on the right one. Action was to set to Allow. For Priority it must be set to a specific number between 100 and 4096, The lower the better. I Chose 300.
<img width="1923" height="897" alt="Figureing out which port would work" src="https://github.com/user-attachments/assets/4ffe3953-06bc-4790-b45d-2adc4e1400f6" />
Once that is done youll come to this screen. to make sure its working press check access once that is pressed and it works just load up RDP again and type in your password and username.
<img width="953" height="666" alt="Finnally getting the port to work without IP" src="https://github.com/user-attachments/assets/88ac0cb1-304d-480d-bb45-271f9462856c" />
After all of that is done it will be able to be used, you can run tests on it and or just work on connecting to the VM
