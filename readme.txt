Working with EBS - Elastic Block Store

    Create an Amazon EBS volume
    Attach and mount your volume to an EC2 instance
    Create a snapshot of your volume
    Create a new volume from your snapshot
    Attach and mount the new volume to your EC2 instance
    
    
	chmod 400 labsuser.pem
	ssh -i labsuser.pem ec2-user@<public-ip>
	df -h
	sudo mkfs -t ext3 /dev/sdf

	sudo mkdir /mnt/data-store
	sudo mount /dev/sdf /mnt/data-store
	echo "/dev/sdf   /mnt/data-store ext3 defaults,noatime 1 2" | sudo tee -a /etc/fstab
	cat /etc/fstab
	sudo sh -c "echo some text has been written > /mnt/data-store/file.txt"
	cat /mnt/data-store/file.txt
	
