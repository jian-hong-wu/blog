請在測試時盡量保持 image & container 的數量, 沒有用到的 image / container 請自行移除, 謝謝 !!
 
Docker 可以想像成一顆硬碟  
image 可以想像成某個 file system 的映像檔案  
container 可以想像成就是把某個 image 打開, 並且可以讓你操作的 virtual machine, 可能在 stop 或 running 狀態  
         所以在 container 上面 local 的修改, 不會影響到其它人或是其它 image  
         要在 container 內修改 mapping 到 server的目錄或檔案, 要加 “sudo”  
 
[ Docker commands – image related ]  
 <p>$ docker build . &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;建立一個 image (細節請自行查閱)  </p>
 <p>$ docker images <p> &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;  查看目前 docker 存了多少 images  </p>
 <p>$ docker rm <image name or ID> <p> &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;  移除 docker 內的某個 image  </p>
 <p>$ docker load < xxxx.gz <p> &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;  載入 image 到 docker 內  </p>
 
[ Docker commands – container related ]  
 <p>$ docker ps -a                                                           查看目前有多少個 containers  
 <p>$ docker rm -f <container name or ID>                                    刪除 container  
 <p>$ docker run --name <container name> -v $PWD:/data -it <image name>      建立一個 container, 並把目前目錄 map 到 container 的 /data 下  
                                                                                                                                若沒有給定 container name, 系統會自動給定一個字串  xxxxxx_xxxxxxx  
$ docker exec -it <container name> bash                                  要求 container 執行 “bash” command (container 已在 running 狀態)  
$ docker start <container name>                                          把在 stop 狀態的 container呼叫起來

&emsp abc

 <p> &emsp;&emsp;&emsp;&emsp;</p>
