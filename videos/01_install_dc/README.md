# 01 Installing the Domain Controller
ACTIVE DIRECTORY #00 Creating our Server + Workstation Virtual Environment - YouTube video - John Hammond


1. Cloning a VM


2. Enabling PSRemoting

    ```shell
    Enable-PSRemoting
    ```
    \\*Type `ipconfig` to check IP Address*\\

    - Adding Windows Server to trusted hosts

        \\*Run Terminal as Administrator*\\

        ```shell
        Start-Service WinRM
        ```
        ```shell
        set-item wsman:\localhost\Client\TrustedHosts -value 192.168.135.129
        ```

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

6. Configure Active Directory Windows Server 2022 Core

    ```shell
    Import-Module ADDSDeployment
    ```
    ```shell
    Install-ADDSForest
    ```

    - Changing DNS Client Server Address

        \\*Check Net IP Address*\\

        ```shell
        GET-NetIPAddress -IPAddress 192.168.135.129
        ```

        \\*Check DNS Server Address*\\

        ```shell
        Get-DNSClientServerAddress
        ```

        ```shell
        Set-DNSClientServerAddress -InterfaceIndex 3 -ServerAddress 192.168.135.129
        ```

7. Adding Workstation to the Domain

    \\*Both Workstation and Domain Controller should be in running state*\\

    ```shell
    Add-Computer -DomainName localhost.com -Credential localhost\Administrator -Force -Restart
    ```
    
