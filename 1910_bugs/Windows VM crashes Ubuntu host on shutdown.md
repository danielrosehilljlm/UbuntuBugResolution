# Windows VM crashes Ubuntu host on shutdown

There is a documented bug in VMWare Workstation Player in which a Windows VM will crash an Ubuntu host on shutdown.

This issue has been discussed in the VMWare community forums [here](https://communities.vmware.com/thread/590662).

## Workaround

You can use this Bash script (not mine) to run the Windows VM. Obviously replace /jlp with your user.

```

#!/bin/sh  
  
#export VMWARE_USE_SHIPPED_LIBS=force  
  
mount |grep "/home/jlp/vmware on /home/jlp/vmware" > /dev/null  
  
if [[ $? -ne 0 ]]; then  
  
  sudo mount -o multithreaded -t fuse.bindfs /home/jlp/vmware /home/jlp/vmware > /dev/null  
  
  if [[ $? -ne 0 ]]; then  
  
    echo "Bindfs mount failed. Please check if bindfs is correctly installed."  
  
    exit 1  
  
  fi  
  
fi  
  
vmplayer "$@"  
  
sudo umount /home/jlp/vmware > /dev/null  
  
exit 0  

```

