Working with EBS:

AIM:

   Create a New EBS Volume.
   Attach the Volume to an Instance.
   Connect to Your Amazon EC2 Instance.
   Create and Configure Your File System.
   Create an Amazon EBS Snapshot.
   Restore the Amazon EBS Snapshot.
   

PROBLEM STATEMENT:

The purpose of this experiment is to understand how Amazon Elastic Block Store (EBS) works with Amazon EC2 instances in AWS cloud computing.
The experiment involves creating storage volumes, attaching them to virtual machines, configuring file systems, creating backups using snapshots,
and restoring data from snapshots.

Explain about the Experiment:

1.A new EBS volume is created in the AWS Management Console.

2.The volume is attached to a running EC2 instance.

3.The EC2 instance is accessed using SSH.

4.A file system is created and mounted on the attached volume.

5.A snapshot of the EBS volume is created for backup purposes.

6.The snapshot is restored by creating a new volume from it.

ALGORITHM:

Steps 1:Login to the AWS Management Console and open the EC2 Dashboard.

Steps 2:Create a new EBS volume by selecting the size, type, and Availability Zone.

Steps 3:Attach the created EBS volume to a running EC2 instance.

Steps 4:Connect to the EC2 instance using SSH, create a file system, and mount the volume.

Steps 5:Create an EBS snapshot, restore it by creating a new volume, and verify the restored data.

COMMANDS:

Include the commands used in the Experiment:

1. Create an EBS Volume:

aws ec2 create-volume \
--availability-zone ap-south-1a \
--size 10 \
--volume-type gp2

2. Describe EBS Volumes:

aws ec2 describe-volumes

3. Attach Volume to EC2 Instance

aws ec2 attach-volume \
--volume-id vol-1234567890abcdef0 \
--instance-id i-1234567890abcdef0 \
--device /dev/sdf

4. Connect to EC2 Instance

ssh -i MyKeyPair.pem ec2-user@<Public-IP-Address>

5. Check Available Disks

lsblk

6. Create File System

sudo mkfs -t ext4 /dev/xvdf

7. Create Mount Directory

sudo mkdir /data

8. Mount the Volume

sudo mount /dev/xvdf /data

9. Verify Mounted File System

df -h

10. Create an EBS Snapshot

aws ec2 create-snapshot \
--volume-id vol-1234567890abcdef0 \
--description "Backup Snapshot"

11. Restore Snapshot by Creating New Volume

aws ec2 create-volume \
--snapshot-id snap-1234567890abcdef0 \
--availability-zone ap-south-1a

12. Detach EBS Volume

aws ec2 detach-volume \
--volume-id vol-1234567890abcdef0

OUTPUT:

REG NUMBER:212224040272

NAME:Reena K

Include your Screenshots Here.

<img width="1918" height="1198" alt="Screenshot 2026-05-12 143324" src="https://github.com/user-attachments/assets/3e85ecf8-87a4-4fc3-9daa-4703742cc35a" />

<img width="1918" height="1193" alt="Screenshot 2026-05-13 114738" src="https://github.com/user-attachments/assets/2989c983-ee09-47bb-a76f-2b2c9c69c0a3" />


<img width="1918" height="1195" alt="Screenshot 2026-05-13 115023" src="https://github.com/user-attachments/assets/d7c590b4-5b6d-417c-bca6-fc2e1f2d04ce" />

<img width="1007" height="509" alt="image" src="https://github.com/user-attachments/assets/4fd59d19-cabd-4e59-a044-454a08577c10" />


RESULT:

Thus, the experiment on working with Amazon EBS was successfully completed. An EBS volume was created, attached to an EC2 instance, configured with a file system, backed up using snapshots, and restored successfully. The experiment provided practical knowledge about persistent cloud storage and backup management in AWS.
