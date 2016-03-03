# Windows Client Buildout

This repo acts as a log for my buildout of my Windows laptop. As I add stuff or change settings, I log it here so pave & restores can go quickly in the future. Feel free to fork & customize to your liking.

## Pave Partition

- Boot while pressing `F8`
- Choose to reset to windows, blowing away all data... or select to download from web (this took ~ 3-45 hours)

## After Pave

- Run through initial setup (login, wifi, etc)
- Rename machine
- Setup power plan High Perf to never sleep
- `PS C:\> Set-ExecutionPolicy Unrestricted -Force`

## Automated Installer

Install Chocolatey (from POSH admin command prompt)

  ```PowerShell
  iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1'))
  ```

Install BoxStarter via Chocolatey

  ```PowerShell
  cinst BoxStarter
  ```

## Manual Installs

-NVM
  - https://github.com/coreybutler/nvm-windows/releases
  - LTS
  - stable
  - run global NPM installs
-SQL Server 2014
  - data tools, management tools complete, client libraries
- Office Pro Plus
- Visio 2016
- Printer drivers
- Camtasia
- SmartSynchronize
- Telerik Just Decompile
- MSFT Online Services SignIn Assistant
  - https://www.microsoft.com/en-us/download/details.aspx?id=41950
- SharePoint Online Management Shell
  - https://www.microsoft.com/en-us/download/details.aspx?id=35588

## Configurations

- Login to
  - Crashplan
  - Dropbox
  - Evernote
  - chrome
- Office Pro Plus
  - login using AAD
  - login to OneNote for MSA & AAD
    - start sync of OneNote
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
- apply license
  - sublime text