## Hi there Im AJ a learning IT/Tech guy

IT Project Troubleshooting on Building a VM And Connecting to It Through RDP

What was needed for this project is a Auzre Virtual Machines,Azure Subscription, Windows 10 enterprise, Windows 10, Chat Gpt, and a can do attitude  

This project is to highlight that most IT Helpdesk errors are to be resolved through troubleshooting
Troubleshooting is a skill that requires using your resources, thinking outside the box and willing do to trial and error until the issue is resolved

Where this project will start is right after creating a resource group in Azure
Right after the Resource group is made Making the virtual machine is the next step
<img width="1452" height="903" alt="Before everything went south" src="https://github.com/user-attachments/assets/65968428-6e73-461d-82bb-245bb3780fd2" />
When creating a virtual machine a few things are needed like Internet, Region , secuiirty type, Image and size
When watching the lab about azure It was noticed that whenever I was attempting to using windows pro 11 It would say that the Image was too big for the subscription being used to create the VM
Which was the first of many issues ran into

 to fix this the selection of windows 10 enterprise version 22h2 - 64 Gen2 then under size i went and searched up where to find less memory as to take up less space. this is where chat gpt came in handy to help me find the exact Size it needed to be to get it to run. The size used was Standard_D2als_v7 - 2vcpus, 4 GiB memory just to shrink it down enough to run. The final step was changing the security type to standard
<img width="1294" height="725" alt="Figuring out which Windows 10 could work with it" src="https://github.com/user-attachments/assets/86b675b0-0ebe-4154-a7c6-f86532afd65f" />
Now As you can see another problem Popped up Right away
This was a Network problem,
