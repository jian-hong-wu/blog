#/bin/bash

DIR=$( cd "$( dirname "${BASH_SOURCE[0]}" )" && pwd )

SRC_SHELL_PATH=$(realpath $(dirname "$0"))

SRC_SERVER_PATH=$(realpath $(dirname "$0"))/sonic-mgmt

cd ..

DST_PATH=${PWD}

var_setting() {

   #generate by python2 jinja2, insatll jinja2 first.
    
   #pip install jinja2

   python2 ${SRC_SHELL_PATH}/server_config_generate.py ${SRC_SERVER_PATH} $2 ${DST_PATH}
}

copy_file() {

   echo "DST path="${DST_PATH}
    
   echo "SRC path="${SRC_SERVER_PATH}
    
   echo "copy file ..."

   cp ${SRC_SERVER_PATH}/ansible/group_vars/all/labinfo.json ${DST_PATH}/ansible/group_vars/all/labinfo.json
   
   cp ${SRC_SERVER_PATH}/ansible/group_vars/eos/creds.yml ${DST_PATH}/ansible/group_vars/eos/creds.yml
   
   cp ${SRC_SERVER_PATH}/ansible/group_vars/fanout/secrets.yml ${DST_PATH}/ansible/group_vars/fanout/secrets.yml
   
   cp ${SRC_SERVER_PATH}/ansible/group_vars/lab/secrets.yml ${DST_PATH}/ansible/group_vars/lab/secrets.yml
    
   cp ${SRC_SERVER_PATH}/ansible/group_vars/sonic/* ${DST_PATH}/ansible/group_vars/sonic/
    
   cp ${SRC_SERVER_PATH}/ansible/group_vars/vm_host/creds.yml ${DST_PATH}/ansible/group_vars/vm_host/creds.yml
    
   cp ${SRC_SERVER_PATH}/ansible/library/minigraph_facts.py ${DST_PATH}/ansible/library/minigraph_facts.py
   
   cp -a ${SRC_SERVER_PATH}/ansible/plugins/callback ${DST_PATH}/ansible/plugins/    
   
   cp ${SRC_SERVER_PATH}/ansible/plugins/connection/switch.py ${DST_PATH}/ansible/plugins/connection/switch.py
   
   cp ${SRC_SERVER_PATH}/ansible/roles/fanout/tasks/rootfanout_connect.yml ${DST_PATH}/ansible/roles/fanout/tasks/rootfanout_connect.yml
   
   cp ${SRC_SERVER_PATH}/ansible/roles/test/templates/* ${DST_PATH}/ansible/roles/test/templates/
   
   cp ${SRC_SERVER_PATH}/ansible/roles/vm_set/tasks/docker.yml ${DST_PATH}/ansible/roles/vm_set/tasks/docker.yml
    
   /# for temporarily let xxx-back back to ovs-bridge
   
   cp ${SRC_SERVER_PATH}/ansible/roles/vm_set/tasks/start.yml ${DST_PATH}/ansible/roles/vm_set/tasks/start.yml
   
   cp ${SRC_SERVER_PATH}/ansible/roles/vm_set/templates/arista.xml.j2 ${DST_PATH}/ansible/roles/vm_set/templates/arista.xml.j2
    
   cp ${SRC_SERVER_PATH}/ansible/roles/vm_set/tasks/main.yml ${DST_PATH}/ansible/roles/vm_set/tasks/main.yml
    
   cp ${SRC_SERVER_PATH}/ansible/vars/docker_registry.yml ${DST_PATH}/ansible/vars/docker_registry.yml

   cp ${SRC_SERVER_PATH}/ansible/ansible.cfg ${DST_PATH}/ansible/ansible.cfg
   
   #cp ${SRC_SERVER_PATH}/ansible/config_sonic_basedon_testbed.yml ${DST_PATH}/ansible/config_sonic_basedon_testbed.yml
   
   cp -a ${SRC_SERVER_PATH}/ansible/automatic ${DST_PATH}/ansible/
   
   cp ${SRC_SERVER_PATH}/ansible/playbook_GetDUTVersion.yml ${DST_PATH}/ansible/playbook_GetDUTVersion.yml
   
   cp ${SRC_SERVER_PATH}/ansible/testcase-cli.sh ${DST_PATH}/ansible/testcase-cli.sh

   /# copy ssh config for fanout switch
    
   mv ${HOME}/.ssh/config ${HOME}/.ssh/config.bak
    
   cp ${SRC_SERVER_PATH}/../ssh_config/config ${HOME}/.ssh/config

}


main() {

if [ $# -eq 0  ]; then

   echo "copy server config fail !"
    
   echo "cmd : server.sh [1-4], e.g. server.sh 2"
   
elif [ $1 == '1' ] || [  $1 == '2' ] || [  $1 == '3' ] || [  $1 == '4' ]; then

   copy_file $1
   
   var_setting ${SRC_SERVER_PATH} $1
    
   cd ${SRC_SHELL_PATH}/../ansible/files
    
   python2 creategraph.py -o lab_connection_graph.xml
    
else

   echo "copy server config fail !"
    
   echo "only support testbed1 ~ testbed4"
    
   echo "cmd : server.sh [1-4] "
   
fi

}

main "$@"
