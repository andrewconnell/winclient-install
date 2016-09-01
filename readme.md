# Windows Client Buildout

This repo acts as a log for my buildout of my Windows laptop. As I add stuff or change settings, I log it here so pave & restores can go quickly in the future. Feel free to fork & customize to your liking.

## Pave Partition

- Within Windows 10
  - **Start** => **Settings** => **Update &amp; Security** => **Recovery**
  - Under **Advanced Startup** select **Restart Now**
- When it reboots
  - **Troubleshoot** => **Reset PC** => **Remove All**
  - *Windows will do some stuff & seem to restart...*
  - Select **Fully Clean Drive**

## After Pave

- Run through initial setup (login, wifi, etc)
- Rename machine
- Setup power plan High Perf to never sleep
- `PS C:\> Set-ExecutionPolicy Unrestricted -Force`

## Automated Installer

Install Chocolatey (from POSH admin command prompt)

  ```PowerShell
  iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
  ```

Install BoxStarter via Chocolatey

  ```PowerShell
  cinst BoxStarter -y
  ```

## Trigger Boxstarter Install

- Launch Boxstarter Shell
- To address https://github.com/mwrock/boxstarter/issues/198, do this:

  ```PowerShell
  choco upgrade chocolatey --version 0.9.10.3 --allow-downgrade
  ```

  - Close Boxstarter Shell
  - Launch Boxstarter Shell

    ```PowerShell
    choco feature enable -n allowEmptyChecksums
    ```

  - Close Boxstarter Shell
- Launch Boxstarter Shell
- Execute following:

  ```PowerShell
  Install-BoxstarterPackage -PackageName [raw URL in GH to the install.boxstarter script]
  ```

- Reboot
- Update Visual Studio:

  ```PowerShell
  Install-BoxstarterPackage -PackageName [raw URL in GH to the vsupdate.boxstarter script]
  ```

## Fix Boxstarter Chocolatey Dependency

- Launch Boxstarter Shell
- To address https://github.com/mwrock/boxstarter/issues/198, do this:

  ```PowerShell
  choco upgrade chocolatey --version 0.9.10.3 --allow-downgrade
  ```

  - Close Boxstarter Shell
  - Launch Boxstarter Shell

    ```PowerShell
    choco feature enable -n allowEmptyChecksums
    ```

  - Close Boxstarter Shell

## Use Boxstarter to Install Apps

- Launch Boxstarter Shell

### Install Core Apps
- Execute following:

  ```PowerShell
  Install-BoxstarterPackage -PackageName https://raw.githubusercontent.com/andrewconnell/winclient-install/master/install.boxstarter
  ```

### Install Visual Studio & Addins

- Execute following:

  ```PowerShell
  Install-BoxstarterPackage -PackageName https://raw.githubusercontent.com/andrewconnell/winclient-install/master/visualstudio.boxstarter
  ```


## Manual Installs

- Synergy
- Camtasia
- NVM
  - https://github.com/coreybutler/nvm-windows/releases
  - LTS
  - stable
  - run global NPM installs
- Office 2016 Pro Plus
  - login and install from O365
- Printer drivers
- SmartGit
- SmartSynchronize
- SQL Server 2014
  - data tools, management tools complete, client libraries
- Visio 2016

### Optional Installs
- MSFT Online Services SignIn Assistant
  - https://www.microsoft.com/en-us/download/details.aspx?id=41950
- SharePoint Online Management Shell
  - https://www.microsoft.com/en-us/download/details.aspx?id=35588

## Configurations

- Windows 10
  - Disable birthday notifications
    - Launch **Calendar** app
    - uncheck all calendars
  - Disable email notifications
    - Launch **Mail** app
    - disable notifications
  - Add O365 account
    - Settings > Accounts
  - Remove all lock screen settings
    - Settings > Personalization > Lock Screen
  - Add Windows Bash
    - Settings > Update & Security > For Developers > Enable Developer Mode
    - Programs & Features > Windows Features > Windows Subsystem for Linux
- Login to
  - Crashplan
  - Dropbox
  - Chrome
- Office Pro Plus
  - login using AAD
  - login to OneNote for MSA & AAD
    - start sync of OneNote
  - Login & setup accounts for Outlook
  - Disable notifications for email & calendar items in Outlook
  - Login & apply license for Visio
- Apply licenses
  - sublime (more below... so wait)
  - snagit
  - Camtasia
- Bluetooth Pair
  - wedge mouse
  - headset
- task bar
  - remove store
  - remove edge
  - add outlook
  - add sublime
  - add onenote
  - add fiddler
  - add vs2015
  - add vscode
- sublime text
  - apply license
  - install package control
  - add packages
    - BracketHighlighter
    - Git
    - Indent XML
    - Preference Helper
    - Pretty JSON
    - SidebarFolders
    - SnippetMaker
    - SublimeCodeIntel
    - Theme - Spacegray
    - TypeScript
    - View In Browser
  - update settings
- vscode
  - install extensions