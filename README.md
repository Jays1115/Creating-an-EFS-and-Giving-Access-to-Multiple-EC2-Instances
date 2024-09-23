<h5>Directory</h5> 

<b>[Tech Portfolio Home](https://github.com/Jays1115/Jalen-Smith.git)</b>
<b>[AWS Projects](https://github.com/Jays1115/AWS-Projects.git)</b>

# Creating-an-EFS-and-Giving-Access-to-Multiple-EC2-Instances

<h2>Description</h2>
Scenario: A company managing pet client data across three branches is experiencing issues with their custom application used for syncing data, which includes images and metadata. They face problems like slow access times, inconsistency, and syncing failures due to storage limitations on local servers. The company is looking for a centralized solution that scales automatically and maintains specific access controls for VIP client folders, accessible only to their concierge team.
<br><br>
Solution: Implementing Amazon Elastic File System (EFS) provides a centralized, scalable storage solution that ensures consistent, real-time access across all branches, supports specific access controls for VIP client folders, and automatically adjusts capacity to prevent sync failures and storage issues.

<h2>Program walk-through:</h2>

<p align="center">
Navigated to the EC2 page to view the currently running EC2 instances: <br/>
<img src="images/Screenshot 2024-09-20 at 12.18.02 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-20 at 12.18.22 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>
