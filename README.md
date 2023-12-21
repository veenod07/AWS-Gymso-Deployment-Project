# AWS-Gymso-Deployment-Project

#Create an EC2 Instance
#Create a VOlume
#attach the volume to the EC2 Instance

Following the below steps:

fdsik -l 
#This command will display information about all the disks and their partitions on your system

fdisk /dev/xvdf 
#this will create the partition table  
df -h 
#command is used to display disk space usage in a human-readable format on Linux

mkfs.ext4 /dev/xvdf1

#Take the backup and move all the images to backup directory

#Temporary mount:
mount /dev/xvdf1 /var/www/html
df -h  If want  to unmount
umount /var/www/html
df -h

#For permanent  writing the mount:
vi /etc/fstab
mount -a   #(if any error it would show here)
df -h     #(or else it would show here)

Move all the data from backup to var/www/html/images

Restart and Check the apache server running:
systemctl restart httpd systemctl status httpd

