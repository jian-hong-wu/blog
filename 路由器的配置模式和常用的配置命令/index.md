[上一頁](https://jian-hong-wu.github.io/blog/)

# 路由器的配置模式和常用的配置命令

掌握路由器的配置模式之間的切換，常用的路由器配置指令，理解IP 資料包路 由過程。
原理
這個實驗由於交換機是即插即用故不用配置三層交換機，只需配置路由器的的
拓撲結構
![](https://jian-hong-wu.github.io/blog/路由器的配置模式和常用的配置命令/1.png)
選擇一臺C2811 路由器，並新增兩臺交換機和兩臺計算機。分別在2 臺計算機上配置IP 地址和閘道器，配置的IP 地址和閘道器如圖所示
(2) 在路由器C2811 上，使用幫助查詢路由器常用配置命令，
![](https://jian-hong-wu.github.io/blog/路由器的配置模式和常用的配置命令/2.png)
(3) 進入路由器f0/0 介面模式，配置IP 地址為192.168.1.1/24。進入路由器f0/1 介面模式，配置IP 地址為192.168.2.1/24
![](https://jian-hong-wu.github.io/blog/路由器的配置模式和常用的配置命令/3.png)
(4) 在路由器全域性模式下使用show ip route 檢視路由表，
![](https://jian-hong-wu.github.io/blog/路由器的配置模式和常用的配置命令/4.png)
(5) 192.168.1.100 與192.168.2.100 之間進行ping 通
![](https://jian-hong-wu.github.io/blog/路由器的配置模式和常用的配置命令/5.png)
6)用show interface f0/0來檢視區域網介面f0/0的詳細資訊，用show interface f0/1
來檢視區域網介面f0/1的詳細資訊。
show interface f0/0
![](https://jian-hong-wu.github.io/blog/路由器的配置模式和常用的配置命令/6.png)
show interface f0/1：
![](https://jian-hong-wu.github.io/blog/路由器的配置模式和常用的配置命令/7.png)
2. 在路由器上用show arp
![](https://jian-hong-wu.github.io/blog/路由器的配置模式和常用的配置命令/8.png)
總結：
從主機192.168.1.1上ping主機192.168.2.1時，資料包是如何傳遞的？主機、交
換機、路由器分別又是如何處理的？
主機192.168.1.1先檢視自己的mac地址如果沒有目標主機mac地址就給交換機進行廣播，如果廣播沒有迴應的，就交給閘道器，閘道器在交給路由器，路由器在去檢視自己的路由表，如果查到最長相似的就交給它，再有它轉發給目標地址

來自 [路由器的配置模式和常用的配置命令](https://www.itread01.com/content/1543884363.html)

