[上一頁](https://jian-hong-wu.github.io/blog/)

當 ssh 連線失敗

ssh: connect to host 192.168.x.xx port 22: Connection refused

首先在伺服器端安裝 openssh-server

$ sudo apt-get install openssh-server

如果要在 Linux 上產生 SSH 登入用的金鑰，可以使用 ssh-keygen 這個指令。在建立金鑰之前，要先建立 ~/.ssh 這個目錄，並設定正確的權限

$ mkdir -p ~/.ssh
$ chmod 700 ~/.ssh

在客戶端產生金鑰 

$ ssh-keygen

在產生金鑰的過程中，會詢問一些問題，對於一般的使用者而言，全部都使用預設值（直接按下 Enter 鍵）即可。

將產生的 id_rsa.pub 檔案內容這個公開金鑰複製到 Linux 伺服器上的 ~/.ssh/authorized_keys 檔案中

之後就可以不用打密碼登入伺服器了

ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQCw7cGMjov3PZ5uDv6WgCVfdniKkRfawaMeAsxEoHjgcV1XqPbIM8YsW1eIaPTO4+pa/thUuRj/EalIGiV7Du+IemuVbewAlB/nZNtkPD8uFCXdEas6mn74dSrJuuSJcT2fjI9vnyWjd+YXdI6cZXqdB78K6ZSSNuCsHnSVhjL4KbLU5wQqEv8g7wHGG82lPdP7VISp2WIknszO0otHby3xJp2I3HBqQJ7BmrsFrRkxtcDyfpK7aMdZCJAfGKJauxmBF0JfsqFV0HgXuMnf8NRptywV/4HuVEuUpfJl+8O3dZJoP7DPxj5teRXoIp4hU9DxrjsqTlWceLhfFKjny5dn75x8DZrbP4qwjnwoFDLKAwYmA04Izb17E4/7BUg23YmYDhBkJ7c0LcMUN6NH5ElJuBn28LIwMOFR95kSpJpOZWbJPIn9xaB5vaNYZxA88M06juIsmZ2wC+OUoUbepOiETXI1uANbC6pqBcWLmRjaDo+Bu1CLqtE2tRhUWzlxalM= hong@hong-X556UQK
