<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Network Files Shares and Permissions</h1>
In this tutorial, we are sharing out resources over the network and creating file shares to allow read, write, or deny access to individual users or groups. <br />


<h2>Video Demonstration</h2>

- ### [Network Files Shares and Permissions](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- File Folders


<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Windows Server 2022

<h2>High-Level Steps</h2>

- Created some sample file shares with various permissions
- Attempting to access file shares as a normal user
- Created an ACCOUNTS Security Group, assigning permissions, and testing access

<h2>Actions and Observations</h2>

<p>
<img src="https://github.com/user-attachments/assets/7de1987b-76f8-4598-8b48-9f1dfc0bfad0" height="80%" width="80%" />
</p>

<br />

<p>
<img src="https://github.com/user-attachments/assets/19299ed3-1566-45e5-b540-422df50a87e5" height="80%" width="80%""/>
 
</p>
<p>
on DC-1 VM, using one of the users in the Employees folder that was created in one of the labs to log in. 
</p>
<p>
  <img src="https://github.com/user-attachments/assets/2499526c-42dc-4b0b-abfa-9a7ece74b5b3" height="80%" width="80%" />
</p>
<p> Successfully logging into the same employee account in Client-1 VM</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/d035bebd-6b7a-46c5-9229-2cfcc4e4ff0d" height="80%" width="80%" />
</p>
<p>
In DC-1 VM as an admin, I was able to create 4 folders (read-access, write-access, no-access, and accounting) on the C:\ drive
</p>
<p>
  <img src="https://github.com/user-attachments/assets/4dccdecc-aeae-4c76-9aab-7fc9272f2680" height="80%" width="80%" />
  <img src="https://github.com/user-attachments/assets/978a7225-d702-4e7e-b9ca-8497b9af6cf6" height="80%" width="80%" />
  <img src="https://github.com/user-attachments/assets/c287189a-7e54-476e-9fee-f6f5ffae3da2" height="80%" width="80%" />
</p>
<p>
  Able to set all Domain Users to read-access to permission level to read only and write-access (read/write). Able to set all Domain Admins to no-access with permission level set to read/write.
</p>
<br />

<p>
  <img src="https://github.com/user-attachments/assets/0bd5a51a-8677-494b-a8e6-50b35d109c17" height="80%" width="80%" />
</p>
<p>
  No-access permission is only for Domain Admins. Since I'm logged into my user BAT.MEX on Client-1 VM, I was denied access.
</p>
<p>
  <img src="https://github.com/user-attachments/assets/585dbfdf-c88b-4c6f-bcfe-3b1009918ad6" height="80%" width="80%" />
</p>
<p>
  Although as a Domain user BAT.MEX, I am granted access to read-access folder, but when trying to create a txt.file, I was unable to since Domain Users are granted read-only access.
</p>

<p>
  <img src="https://github.com/user-attachments/assets/a45427bf-0c36-403f-98b0-8a52b6b666da" height="80%" width="80%" />
</p>
<p>
  write-access was set to read/write for Domain Users. So as someone like BAT.MEX is able to access, read, and write in the folder.
</p>

<p>
  <img src="https://github.com/user-attachments/assets/9308e85e-3944-46a0-9672-3b79125479b5" height="80%" width="80%" />
</p>

<p>
  On DC-1 as an admin, I'm able to read and write on the read-access folder.
  
</p>

<p>
  <img src="https://github.com/user-attachments/assets/a2806f6d-1bba-4e6a-bef9-4621ef52b4fd" height="80%" width="80%" />
  
</p>
<p>
  On DC-1, I created an Organizational Unit called SECURITY GROUPS and in that group, I was ale to create ACCOUNTANTS.
</p>
<p>
  <img src="https://github.com/user-attachments/assets/0c81f603-7b1b-4a4b-9dba-e7c47fb0cbe9" height="80%" width="80%" />

</p>
<p>
  In my DC-1 VM, I'm able to grant access in the accountants folder to ACCOUNTANTS with a permission level to read/write.
</p>

<br />
<p>
  <img src="https://github.com/user-attachments/assets/8513e1b5-c7cb-47e2-b9f6-bf988ac2fb39" height="80%" width="80%" />
  
</p>
<p>
  Logging back into Client-1 VM on user BAT.MEX, I was unable to access accountants folder due to it only being for accountants.
</p>
<p>
  <img src="https://github.com/user-attachments/assets/6a6585f3-ba19-4cf8-9e17-bd74053b1b14" height="80%" width="80%" />
</p>
<p>
  Created and granted access for user BAT.MEX for accountants folder. 
</p>

<p>
  <img src="https://github.com/user-attachments/assets/7469fa36-9db8-4c41-ac10-a411d0de5604" height="80%" width="80%" />
</p>
<p>Permission and access granted for user BAT.MEX on Client-1 VM. BAT.MEX is now able to read/write on Accountants. </p>
