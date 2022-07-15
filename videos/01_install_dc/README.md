# 01 Installing the Domain Controller
ACTIVE DIRECTORY #00 Creating our Server + Workstation Virtual Environment - YouTube video - John Hammond


1. Cloning a VM
    Installing VMware Tools On command line VM

2. Enabling PSRemoting
    Adding Windows Server to trusted hosts

3. Use `sconfig` to:
    - Change the hostname
    - Change the IP address to static
    - Change the DNS server to our own IP address

4. Install the Active Directory Windows Feature

    ```shell
    Install-WindowsFeature AD-Domain -IncludeManagementTools
    ```

5. Chocolatey Installation
    - Choco install git
    - git clone
    - Choco install vscode
    
