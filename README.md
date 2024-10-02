# Ops
usefull cmd

## search in previous cmd
ctrl+r 

# Kubernetes

## Set default namespace 
kubectl config set-context --current --namespace='namespace'

## list env var of deployment
kubectl set env deployment/'deployment-NAME' --list

## Scale deployment 
kubectl scale deploy my-awesome-deployment --replicas=0

# Linux helper

# network
apt install iperf3

iperf3 -s

iperf3 -c <Server-2-IP>

## List disks :
fdisk -l
lsblk

## For NVME disks, you must install nvme-cli and list the disks :
apt-get install -y nvme-cli
nvme list
parted -l

## Retrieve the listing results and adapt the commands below :
nvme smart-log /dev/nvme0n1
nvme smart-log /dev/nvme1n1

## verify disk status, for each NVME Disk  :
smartctl -a /dev/nvmeXnX
smartctl -a /dev/nvmeXnX

## verify raid status:
cat /proc/mdstat

## test disk 
https://help.ovhcloud.com/csm/fr-public-cloud-compute-storage-test-disk-speed?id=kb_article_view&sysparm_article=KB0051277

## List the partition tables
fdisk -l

## find a filesystem 
findmnt

## List mount device on boot
cat /etc/fstab

## Sort disk usage by size the bigger last
du -hs * | sort -h

## decode base64
echo "stuff the be decode" | base64 --decode

## replace place holder in file and replace by env var
sed -e 's|PLACEHOLDER_1|'"$var_1"'|g' \
    -e 's|PLACEHOLDER_2|'"$var_2"'|g' \
    -e 's|PLACEHOLDER_3|'"$var_3"'|g' \
    input_file_path
