[上一頁](https://jian-hong-wu.github.io/blog/testcase/)

function add_topo

{

 topology=$1
  
 passwd=$2
  
 shift
  
 shift
  
 echo "Deploying topology '${topology}'"

 read_file ${topology}

 echo "$dut" "$duts"

 if [ -n "$sonic_vm_dir" ]; then
  
   ansible_options="-e sonic_vm_storage_location=$sonic_vm_dir"
      
 fi

 ANSIBLE_SCP_IF_SSH=y ansible-playbook -i $vmfile testbed_add_vm_topology.yml --vault-password-file="${passwd}" -l "$server" \
 
   -e topo_name="$topo_name" -e duts_name="$duts" -e VM_base="$vm_base" \
        
   -e ptf_ip="$ptf_ip" -e topo="$topo" -e vm_set_name="$vm_set_name" \
        
   -e ptf_imagename="$ptf_imagename" -e vm_type="$vm_type" -e ptf_ipv6="$ptf_ipv6" \
   
   $ansible_options $@

 if [[ "$ptf_imagename" != "docker-keysight-api-server" ]]; then
  
   ansible-playbook fanout_connect.yml -i $vmfile --limit "$server" --vault-password-file="${passwd}" -e "dut=$duts" $@
   
 fi

  /# Delete the obsoleted arp entry for the PTF IP
  
  ip neighbor flush $ptf_ip

  echo Done
  
}
