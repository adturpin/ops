# Ops
usefull cmd


# Kubernetes
kubectl config set-context --current --namespace='namespace'

kubectl set env deployment/'deployment-NAME' --list

# Linux helper
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
