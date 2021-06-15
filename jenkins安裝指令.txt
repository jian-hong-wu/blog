先安裝java:

sudo apt-get update
sudo apt-get upgrade
sudo apt-get install default-jdk
javac -version   (測試)

安裝jenkin:

wget -q -O - https://jenkins-ci.org/debian/jenkins-ci.org.key | sudo apt-key add -  
sudo sh -c 'echo deb http://pkg.jenkins-ci.org/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'  
sudo apt-get update
sudo apt-get install jenkins  

執行jenkin:

sudo service jenkins start  
開啟 Jenkins 網頁頁面 http://yourserverIP:8080
出現畫面後需要取得初始的 admin 密碼
sudo cat /var/lib/jenkins/secrets/initialAdminPassword  
輸入完密碼後即可選擇安裝所需的插件，系統會自動安裝建議的套件

參考
https://oranwind.org/-devops-jenkins-yu-centos-ubuntu-an-zhuang-jiao-xue/
