
<h1><p align="center"> Using Vagrant on your personal computer Public </h1></p></font>

## Why use Virtual Machines? And why Vagrant?
We’re glad that you’re adapting to the Framework! **Always ask why!**  
It is important to ask yoursef: *“Why am I not just developing on my computer? I have all the tools I need!”.

### My machine vs. virtual environments
Your computer’s environment - whether it’s Windows, MacOS or a Linux distribution - will change a lot over time, with or without you noticing. You will install applications, games, tools, … that will require and install different dependencies and at the end of the day you can end up having completely different behaviors or even have something not work because of software conflicts.

We won’t go into the details of Virtual Machines, but as their name tells, they are Virtual “Computers” that will emulate everything from the CPU to the RAM and Disk. Virtual Machines in the context of development are a means to **isolate and maintain a stable environment** that will basically **run the same way on any host** (any computer). This way, you can have any software installed on your Windows, MacOS, or whatever Linux distribution; your Virtual Machine will run its own environment, have its own programs, with their own versions, etc.

Using virtual environments prevents developers from saying **“I don’t understand, it works on my machine …”**. Here at School, we want to make sure that you have access to the same environment that will be used to correct your work (the Checker).

## The tools
There are multiple tools out there that can help you create and manage virtual environments (notice that we use the term “virtual environment” here, as such environemnt is not necessarily a VM. Technologies using containerization allow one to manage virtual environments as well).  
We are using two tools at school: **VirtualBox** and **Vagrant**.

- **VirtualBox** is a Virtual Machine provider. The virtual machines themselves will be spawned using VirtualBox. VirtualBox is free and lightweight, which make it a perfect choice for us.

- **Vagrant** is a tool that sits on top of a VM provider. Again, we chose to use VirtualBox as a provider, but other providers exist out there and Vagrant offers the possibilty to use dfferent providers (More info [here](https://developer.hashicorp.com/vagrant/docs/providers)). Just like VirtualBox, we choose to use Vagrant because it is free, reliable and well maintained. Keep in mind that the purpose here is to use Virtual environments, and both VirtualBox and Vagrant are just means to achieve this purpose.

## Alternatives
As mentioned previously, using VirtualBox and Vagrant at school doesn’t mean that all companies are going to work exactly the same way. Different tools are used, as well as different development workflows. We want you to understand how important it is to isolate your development environment from any host machine, whether it’s your personal computer or one of the school’s computers.

Here are some examples of other softwares out there that are widely used to manage virtual environments:

- The **VMWare** products 
  - VMWare is one of the biggest virtualization company in the industry.  
  - It is safe to say that their tools are among the most reliable.  
  - On the other hands, most of their tools come for a price.

- **Docker**  
  - Containerization is a very good and efficient alternative to VMs for development environments  
  - Containers are much more lightweight than VMs, thus much faster to start and stop.  
  - The inconvinience of containers is that they sit on top of your OS. Unlike virtual machines, they don’t emulate the hardware, but rather share your machine’s hardware. We won’t go into the details of how containerization works, but to keep it simple, that means that if you run MacOS, it is not possible to run a Linux or Windows container. (Docker makes it work using VMs).  
  - More info [here](https://developer.hashicorp.com/vagrant/intro/vs)

## Conclusion
VirtualBox and Vagrant together allow you to manage and ship isolated development environments. Those isolated environments in the context of the school (and in the future, in the context of a company) allow you to match the environment we use to automatically check your work.  
Although both VirtualBox and Vagrant are widely used in the industry, it doesn’t mean it is the only means to achieve virtualization, and other tools exist with their pros and cons.

---

## How to install Vagrant on your personal computer:

### Mac OSx
1. Download VirtualBox from [this link](https://www.virtualbox.org/wiki/Downloads)
2. Install VirtualBox
3. Download Vagrant from [this link](https://developer.hashicorp.com/vagrant/install)
4. Install Vagrant
5. Open the Terminal application:  
    - Now you will execute command line in your Terminal (each of them start with `$`)
    - Add the **Ubuntu 20.04 (Focal)** image to your box list:  `$ vagrant box add ubuntu/focal64`  
        *Warning: this step can take time*  
    - Many other images are available [here](https://portal.cloud.hashicorp.com/vagrant/discover)
7. Create your first virtual machine:  
   `$ vagrant init ubuntu/focal64` → > it will generate a Vagrantfile with `base = "ubuntu/focal64"`  
   *you don’t have to execute this command line everyday, only once, to create a new virtual machine*

<p align="center">
  <img src="https://github.com/user-attachments/assets/6f82fe1c-655e-41a0-9770-7f9671a10fd6" alt="Image"/>
</p>

   `$ vagrant up` → it will start your virtual machine  

<p align="center">
  <img src="https://github.com/user-attachments/assets/1e9d7ce8-bd76-47ab-bb0c-ee0924db2fb0" alt="Image"/>
</p>

   `$ vagrant ssh` → now you are inside your virtual machine

<p align="center">
  <img src="https://github.com/user-attachments/assets/2c0562b0-5ecc-4bb8-ab95-2e0a215bf496" alt="Image"/>
</p>

### Windows
1. Download VirtualBox from [this link](https://www.virtualbox.org/wiki/Downloads)
2. Install VirtualBox
3. Download Vagrant from [this link](https://developer.hashicorp.com/vagrant/installs)
4. Install Vagrant
5. Open the [command prompt](https://www.lifewire.com/how-to-open-command-prompt-2618089)
6. Add the **Ubuntu 20.04 (Focal)** image to your box list:  
   - `C:\Users\julien> vagrant box add ubuntu/focal64`  
   *Warning: this step can take time*  
    Many other images are available [here](https://portal.cloud.hashicorp.com/vagrant/discover)

  <p align="center">
  <img src="https://github.com/user-attachments/assets/2b7f4bcf-0c43-4762-a2b1-5548a4127f74" alt="Image"/>
</p>

  - Create your first virtual machine:  
    - `C:\Users\julien> vagrant init ubuntu/focal64` → it will generate a Vagrantfile with `base = "ubuntu/focal64"` 
    *-you don’t have to execute this command line everyday, only once, to create a new virtual machine*

<p align="center">
  <img src="https://github.com/user-attachments/assets/fc321377-21c6-498d-a514-9b9c4f8b1591" alt="Image"/>
</p>

   - `C:\Users\julien> vagrant plugin install vagrant-vbguest` → to avoid issue with the last version of Vagrant (2.2.4 or latest)  
   - `C:\Users\julien> vagrant up` → it will start your virtual machine
<p align="center">
  <img src="https://github.com/user-attachments/assets/1d9c2af2-68ba-45e4-88e2-ceb2f163d80e" alt="Image"/>
</p>

   `C:\Users\julien> vagrant ssh` → now you are inside your virtual machine.

<p align="center">
  <img src="https://github.com/user-attachments/assets/419ec2ea-2c03-4af6-965d-aa107695d66d" alt="Image"/>
</p>


### Ubuntu
1. Open the Terminal application:  
   - Now you will execute command line in your Terminal (each of them start with `$`)
2. Install VirtualBox:  `$ sudo apt-get install virtualbox`
3. Install Vagrant:  `$ sudo apt-get install vagrant`
4. Add the **Ubuntu 20.04 (Focal)** image to your box list: `$ vagrant box add ubuntu/focal64`  
   **Warning: this step can take time**  
   - Many other images are available [here](https://portal.cloud.hashicorp.com/vagrant/discover)
5. Create your first virtual machine:  
   `$ vagrant init ubuntu/focal64` → it will generate a Vagrantfile with `base = "ubuntu/focal64"` 
    *-you don’t have to execute this command line everyday, only once, to create a new virtual machine*
   `$ vagrant up` → it will start your virtual machine  
   `$ vagrant ssh` → now you are inside your virtual machine.
