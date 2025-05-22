### Overview:

A simple walkthrough of installing kali linux 2025 in virtual box on windows host as part of my cybersecurity lab setup

### Prerequisites:

**1. Enabling virtualization by rebooting into BIOS settings**

**2. Virtual box [latest version] (https://www.virtualbox.org/wiki/Downloads)**

**3. Kali linux iso image (https://www.kali.org/get-kali/#kali-installer-images)**

### Installation Steps:

**1. Install virtual box**
  - run the installer and accept all default options
  - also install extension pack when prompted
  
**2. Download kali linux installer iso from the official site**
  - make sure to download installer iso and not the live version
   
**3. Create a vm in virtual box:**
  - open virtualbox and click new
  - name your vm
  - attach the kali iso by clicking the arrow next to iso image and choosing the iso folder from your file explorer
  - type and subtype will be ubunto by default but you can choose debian since kali is based on debian
  - allocate how much virtual resources the vm will use (i recommend 25gb hard disk /4gb ram/2 cpus)

**4. Start the vm and install kali**
  - click start and select graphical installation
  - setup credentials and continue with default options

**5. Post installation tips**
  - keep kali updated by running the following command in terminal: (sudo apt update && sudo apt upgrade -y)

### Lessons learned:
  - don’t forget to enable virtualization in your BIOS, this one caught me off guard at first.
  - learned the difference between installer iso and live iso.
  - i initially allocated 15gb of virtual storage but the final installation step kept failing, and after some research i discovered that the minimum virtual storage should be 25gb.
