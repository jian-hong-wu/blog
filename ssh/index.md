[上一頁](https://jian-hong-wu.github.io/blog/)

# 當 ssh 連線失敗

ssh: connect to host 192.168.x.xx port 22: Connection refused

## 在 Linux 伺服器端安裝 openssh-server

$ sudo apt-get install openssh-server

安裝完畢後，在相同網域之下即可使用 ssh 連線

若不想要輸入密碼登入伺服器則需要使用金鑰

要在 Linux 上產生 SSH 登入用的金鑰，可以使用 ssh-keygen 這個指令。在建立金鑰之前，要先建立 ~/.ssh 這個目錄，並設定正確的權限

$ mkdir -p ~/.ssh  
$ chmod 700 ~/.ssh

在客戶端產生金鑰 

$ ssh-keygen

在產生金鑰的過程中，會詢問一些問題，對於一般的使用者而言，全部都使用預設值（不須輸入直接按下 Enter 鍵）即可。

將產生的 id_rsa.pub 檔案內容這個公開金鑰複製到 Linux 伺服器上的 ~/.ssh/authorized_keys 檔案中

之後就可以不用打密碼登入伺服器了

公開金鑰範例：

ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQCw7cGMjov3PZ5uDv6WgCVfdniKkRfawaMeAsxEoHjgcV1XqPbIM8YsW1eIaPTO4+pa/thUuRj/EalIGiV7Du+IemuVbewAlB/nZNtkPD8uFCXdEas6mn74dSrJuuSJcT2fjI9vnyWjd+YXdI6cZXqdB78K6ZSSNuCsHnSVhjL4KbLU5wQqEv8g7wHGG82lPdP7VISp2WIknszO0otHby3xJp2I3HBqQJ7BmrsFrRkxtcDyfpK7aMdZCJAfGKJauxmBF0JfsqFV0HgXuMnf8NRptywV/4HuVEuUpfJl+8O3dZJoP7DPxj5teRXoIp4hU9DxrjsqTlWceLhfFKjny5dn75x8DZrbP4qwjnwoFDLKAwYmA04Izb17E4/7BUg23YmYDhBkJ7c0LcMUN6NH5ElJuBn28LIwMOFR95kSpJpOZWbJPIn9xaB5vaNYZxA88M06juIsmZ2wC+OUoUbepOiETXI1uANbC6pqBcWLmRjaDo+Bu1CLqtE2tRhUWzlxalM= hong@hong-X556UQK

ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQDGW6ZnVwQzbk30fZ37fQCFW3+xlcwqQMbSoexddB452tPt2o+yc9MJ0ZWHDEu/Ke4LJ6mkRFUghBccggzvRC2tPv5+XqSP1SQKJINrhewKdvpSm57bljTPQFb1v9yW/M0QlHFFhHSDGfBJTf5NBAXa7wKbzZIZVA8I1xlh31wZo9bnLrm9b9xThvsRrNm+RHiTUIt1PdWPSoq1f9/k1wNmgmupBdj5qGENEunVZSFKKo2DTTC6/K2HLfsvNoWrcsH30NtsR4uQk4H/I7gGxWeXlzvKdTMrGqu0dHmZBML/g/VBHBOeavBzWkDUe0LE5W+HY2oXbZ6sHHCE+jRX2xMiX/gK6YnUHA0TdyEMGjdeZjkqTlT6Z6+xYXCasU9rhdIIhxKPhvSuGqSls2CW+uiYh4c2UUt0fChYmz3VRrBD1b19TmlEg9lzuzyyuZal6ffp9fTMM3Ru7QzIBTbD4PhQisT0DicfQGMwe/o8Hb2zvaoVlvySEQBu5JmIlm/uar0= accton@accton-SB101-UR

## 使用 Windows 設定安裝 OpenSSH

若要使用 PowerShell 安裝 OpenSSH，請以系統管理員身分執行 PowerShell。 若要確認 OpenSSH 可供使用，請執行下列 Cmdlet：

$ Get-WindowsCapability -Online | ? Name -like 'OpenSSH*'

如果尚未安裝，這應該會傳回下列輸出：

Name  : OpenSSH.Client~~~~0.0.1.0  
State : NotPresent

Name  : OpenSSH.Server~~~~0.0.1.0  
State : NotPresent

然後，視需要安裝伺服器或用戶端元件：

#Install the OpenSSH Client  
Add-WindowsCapability -Online -Name OpenSSH.Client~~~~0.0.1.0

#Install the OpenSSH Server  
Add-WindowsCapability -Online -Name OpenSSH.Server~~~~0.0.1.0

這兩個都應該會傳回下列輸出：

Path          :  
Online        : True  
RestartNeeded : False

#啟動及設定 OpenSSH 伺服器  
#Start the sshd service  
$ Start-Service sshd

#OPTIONAL but recommended:  
$ Set-Service -Name sshd -StartupType 'Automatic'

#Confirm the firewall rule is configured. It should be created automatically by setup.  
$ Get-NetFirewallRule -Name *ssh*

#There should be a firewall rule named "OpenSSH-Server-In-TCP", which should be enabled  
#If the firewall does not exist, create one  
$ New-NetFirewallRule -Name sshd -DisplayName 'OpenSSH Server (sshd)' -Enabled True -Direction Inbound -Protocol TCP -Action Allow -LocalPort 22

之後便可以使用 ssh 連線
