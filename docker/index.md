[上一頁](https://jian-hong-wu.github.io/blog/)

#### 安裝

$ sudo apt-get remove docker docker-engine docker.io containerd runc

$ sudo apt-get update

$ sudo apt-get install \

  apt-transport-https \
  
  ca-certificates \
  
  curl \
  
  gnupg-agent \
  
  software-properties-common
  
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

$ sudo apt-key fingerprint 0EBFCD88

$ sudo add-apt-repository \

  "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
  
  $(lsb_release -cs) \
  
  stable"
  
$ sudo apt-get update

$ sudo apt-get install docker-ce docker-ce-cli containerd.io

$ sudo docker run hello-world

$ sudo chmod 777 /var/run/docker.sock

#### 指令
$ docker images (-a -q)

$ docker search -s 30 "image" ##只搜尋超過30星的image

$ docker pull "image"

$ docker rmi -f "image"

$ docker rmi -f $(docker images -a -q) ##刪除全部images

$ docker run -it --name "name" "image"

$ docker run -d --name "name" "image" ##不進入 container 運行



$ docker ps -l ##列出目前在運行的containers

$ docker ps -a ##列出所有曾運行過的containers

$ docker ps -q ##只顯示containers ID

$ docker start "container ID"

$ docker stop "container ID"

$ docker kill "container ID" ##強制停止

$ docker rm -f "container ID"

$ docker rm -f $(docker ps -a -q) ##刪除全部container

$ docker log -t -f --tail 3 "container ID" ##增加時間標記 不停追加 只顯示最後三個

$ docker top "container ID" ##顯示container的進程

$ docker inspect "container ID" ##顯示container的詳細進程

$ docker exec -it "container ID" "command" ##在container打開新的終端執行，開啟新進程

$ docker attach "container ID" ##進入container終端，不開啟新進程

$ exit ##停止退出

$ ctrl+P+Q ##不停止退出

$ docker cp "container ID":"path1" "path2" ##從container複製檔案到本機



$ docker run -it -p 8888:8080 "container ID"

$ docker run -it -P 'container ID"

$ docker commit -m="信息" -a="作者" "舊container ID" "新container's name" ##從舊container建立新image

$ docker run -it -v "path1": "path2" "image"

$ docker run -it -v "path1": "path2":or "image" ##container只可讀取

$ docker build -f "path" -t "name" . ##用dockerfile创建镜像

$ docker save -o XXX.tar "image's name" ##備份 image 到本地

$ docker load -i XXX.tar ##從檔案載入 image

### dockerfile體系結構

FROM ##基礎鏡像

MAINTAINER ##鏡像維護者姓名及郵件地址

RUN ##容器建構時需要運行的命令

EXPOSE ##容器對外的端口

WORKDIR ##創建容器後，終端默認登入的工作目錄

ENV ##用來在建構鏡像過程中設置環境變量

ADD ##將主機目錄下的文件複製進鏡像且ADD命令會自動處理URL和解壓縮

COPY ##複製文件和目錄到鏡像中。將從建構上下文目錄中<原路徑>的文件/目錄複製到新一層的鏡像內的<目標路徑>位置

VOLUME ##用於數據保存和持久化工作

CMD ##指定一個容器啟動時要運行的命令。Dockerfile中可以有多個CMD指令，但只有最後一個生效，會被docker run之後的參數替換

ENTRYPOINT ##指定一個容器啟動時要運行的命令。

ONBUILD ##建構一個被繼承的Dockerfile時運行命令，父鏡像在被子鏡像繼承後父鏡像的onbuild被觸發

