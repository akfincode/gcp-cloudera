## Cloudera on Google Cloud

Portal for detailed steps to install CDH 5 on Google Cloud and custom application integration.

## Installation

Spin up multiple GCP compute instances (Nodes). Verify all prices / charges.

SSH into each node and execute the following:

vi /etc/ssh/sshd_config

	PermitRootLogin yes
	PubkeyAuthentication yes
	AuthorizedKeysFile /.ssh/authorized_keys
	ChallengeResponseAuthentication yes

/bin/systemctl restart sshd  

Generate SSH keys
	ssh-keygen
	
ssh-copy-id root@node2  
ssh root@node2  
sysctl -w vm.swappiness=0  
sudo systemctl disable firewalld  
sudo systemctl stop firewalld  

Disable SELINUX
	vi /etc/selinux/config  
	Restart instances  
	Verify: getenforce   
	
Download and Install Cloudera:
	wget http://archive.cloudera.com/cm5/installer/latest/cloudera-manager-installer.bin  
	chmod u+x cloudera-manager-installer.bin  
	./cloudera-manager-installer.bin  
	Follow Cloudera Install Steps  

Start Cloudera Server:  
	sudo service cloudera-scm-server start  
	Verify:   
		netstat -a | grep 7180  
		http://IP:7180/cmf/login (default credentials)  


