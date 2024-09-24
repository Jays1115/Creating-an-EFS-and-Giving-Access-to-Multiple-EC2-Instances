<h5>Directory</h5> 

<b>[Tech Portfolio Home](https://github.com/Jays1115/Jalen-Smith.git)</b> /
<b>[AWS Projects](https://github.com/Jays1115/AWS-Projects.git)</b>

# Creating an EFS and Giving Access to Multiple EC2 Instances

<h2>Description</h2>
Scenario: A company managing pet client data across three branches is experiencing issues with their custom application used for syncing data, which includes images and metadata. They face problems like slow access times, inconsistency, and syncing failures due to storage limitations on local servers. The company is looking for a centralized solution that scales automatically and maintains specific access controls for VIP client folders, accessible only to their concierge team.
<br><br>
Solution: Implementing Amazon Elastic File System (EFS) provides a centralized, scalable storage solution that ensures consistent, real-time access across all branches, supports specific access controls for VIP client folders, and automatically adjusts capacity to prevent sync failures and storage issues.

<h2>Program walk-through:</h2>

<p align="center">
Navigated to the EC2 page to view the currently running EC2 instances: <br/>
<img src="images/Screenshot 2024-09-23 at 6.16.43 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 6.18.14 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

<p align="center">
Navigate to the security groups page via the left sidebar: <br/>
<img src="images/Screenshot 2024-09-23 at 6.20.28 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

<p align="center">
Established a security group specifically for the Elastic File System to control traffic between the EC2 instances and the EFS: <br/>
<img src="images/Screenshot 2024-09-23 at 6.20.42 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 6.24.56 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 6.26.03 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 6.26.17 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

<p align="center">
Navigated to the EFS page: <br/>
<img src="images/Screenshot 2024-09-23 at 6.29.47 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 6.30.02 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

<p align="center">
Initiated the creation of the Elastic File System and disabled automatic backups to optimize storage costs and manage data redundancy according to our specific backup strategy requirements: <br/>
<img src="images/Screenshot 2024-09-23 at 6.32.33 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 6.33.02 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 6.34.02 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

<p align="center">
Added a mount target in the us-east-1a availability zone and assigned it to the newly created security group for enhanced security configuration: <br/>
<img src="images/Screenshot 2024-09-23 at 6.35.42 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

<p align="center">
EFS created: <br/>
<img src="images/Screenshot 2024-09-23 at 6.36.41 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

<p align="center">
Accessed the Elastic File System to retrieve the EFS mount helper command: <br/>
<img src="images/Screenshot 2024-09-23 at 6.43.14 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 6.43.54 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

<p align="center">
Back to EC2 instances: <br/>
<img src="images/Screenshot 2024-09-23 at 6.45.23 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 6.45.50 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

<p align="center">
Connected to web server 1 via the session manager: <br/>
<img src="images/Screenshot 2024-09-23 at 6.46.50 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 6.47.45 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

<p align="center">
Executed the following using the command line:
- Ran “sudo -i” to become root user
- Installed EFS utilities using this command: sudo yum install -y amazon-efs-utils
- Created a data directory: mkdir data
- Copied and pasted the mounting command: sudo mount -t efs -o tls fs-0bcccb26039ed930b:/ data
- Created a log file: sudo bash -c "cat >> efs-1-setup.log”
- Added a record to the log: efs-1 mounted in site A <br/>
<img src="images/Screenshot 2024-09-23 at 6.49.31 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 6.54.34 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

<p align="center">
Navigated back to EFS: <br/>
<img src="images/Screenshot 2024-09-23 at 7.06.47 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 7.06.59 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

<p align="center">
In the network tab, clicked “manage”, to add another ec2 instance as a mounted target: <br/>
<img src="images/Screenshot 2024-09-23 at 7.09.39 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 7.11.05 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 7.14.32 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

<p align="center">
Repeated the mounting process on the second an third EC2 instance using the Session Manager connection, installing the required EFS utilitizes, ensuring the EFS was properly attached, and updated the log file to reflect the successful configuration for both instances.
</p>
