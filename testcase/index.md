# testcase

[上一頁](https://jian-hong-wu.github.io/blog/)

docker run -it --name test sonic-mgmt-dev:ec202006 bash

cd sonic-mgmt/

cd server_config

./server.sh 2

cd ../ansible/

vi testbed.csv

./testbed-cli.sh -b VM0200 add-topo 2-7_t0 ~/.password -e ptf_imagetag=ec2020006

![圖(一)](https://jian-hong-wu.github.io/blog/pic/1.jpg)

ansible-playbook -i lab config_sonic_basedon_testbed.yml -l as5812-54x -e testbed_name=2-7_t0 -e deploy=true -e save=true

![圖(二)](https://jian-hong-wu.github.io/blog/pic/2.jpg)

ansible-playbook -i lab --limit as5812-54x test_sonic.yml -e testbed_name=2-7_t0 -e  testcase_name=syslog -vvvv

![圖(三)](https://jian-hong-wu.github.io/blog/pic/3.jpg)

cd ../tests

py.test --inventory=lab --host-pattern=2-7_t0 --module-path ../ansible/library/ --testbed=2-7_t0 --testbed_file=../ansible/testbed.csv ./syslog/test_syslog.py --log-level=DEBUG -vvvv --show-capture=stdout --duration=0

![圖(四)](https://jian-hong-wu.github.io/blog/pic/4.jpg)

![圖(五)](https://jian-hong-wu.github.io/blog/pic/5.jpg)

cd ../ansible

./testbed.cli.sh remove-topo 2-7_t0 ~/.password

exit

docker rm test

