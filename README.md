<img width="298" alt="04_All GPOs" src="https://github.com/user-attachments/assets/e36eb7a4-e8ee-4ca4-930c-441da2d7f604" /># 🛡️ Active Directory Departmental Structure & Group Policy Project

This project simulates a real-world organizational structure in **Windows Server Active Directory**, implementing **organizational units (OUs)**, **user and group management**, **NTFS folder permissions**, and **Group Policy Objects (GPOs)** tailored to each department.

---

## 🧰 Tools & Technologies Used

- **Windows Server 2025**
- **Active Directory Domain Services (AD DS)**
- **Group Policy Management Console (GPMC)**
- **File and Storage Services**
- **NTFS Permissions**
- **Organizational Units (OUs)**
- **PowerShell (Optional)**
- **VirtualBox (for lab virtualization)**

---

## 📚 Skills Demonstrated

- Creating and managing **Organizational Units (OUs)**
- Creating **users**, **security groups**, and managing group membership
- Setting **NTFS folder permissions** for controlled access
- Designing and applying **Group Policy Objects (GPOs)**
- Implementing **department-specific security controls**
- Testing and troubleshooting access rights and policy application

---

## 🧩 Project Objective

- Create 3 departments: **IT**, **Sales**, and **Finance**
- Each department contains **3 users**
- Assign **folder access permissions** per department
- Grant **IT Manager Read-Access** to both Sales and Finance department folders
- Apply **unique GPOs** to each department for operational control

---

## ✅ Project Steps

### 1. 🧱 Create Organizational Units (OUs)
- Open **Active Directory Users and Computers (ADUC)** (`dsa.msc`)

<img width="1258" alt="01-OUs" src="https://github.com/user-attachments/assets/5c20418c-b1b6-40cf-9462-bf30b387640f" />


- Right-click the domain → `New > Organizational Unit`

<img width="535" alt="02-OU" src="https://github.com/user-attachments/assets/9c2344a5-1d3d-4d51-ba8a-7bf4182536a9" />


  - `IT`
  
 <img width="379" alt="03-Create-IT" src="https://github.com/user-attachments/assets/eaa48a97-061b-468b-8cc9-3f9050ff1e83" />

  
  - `Sales`
    
 <img width="344" alt="04-Create-Sales" src="https://github.com/user-attachments/assets/5255bdba-5f74-4724-bc2f-7844e9721dde" />

    
  - `Finance`
    
<img width="347" alt="05-Create-Finance" src="https://github.com/user-attachments/assets/2d8a74ae-4c21-4134-8b43-e0917532fd58" />


 - `Three OUs Created`
  
<img width="544" alt="06-OUsCreated" src="https://github.com/user-attachments/assets/9876b105-aba3-42b5-9127-20292d204a71" />

   
---

### 3. 👤 Create Users for Each Department
- In each OU:
  - **IT**: right-click on the OU: then click 'New'
<img width="813" alt="07-IT-Manager" src="https://github.com/user-attachments/assets/baacf694-8a79-4a4f-9085-28eb691931d4" />

    
- `Bob Marley` 
<img width="346" alt="08-BMarley-IT-Manager" src="https://github.com/user-attachments/assets/1c97ba4d-c900-40d2-b50d-3dcad8552919" />


<img width="344" alt="09-Password" src="https://github.com/user-attachments/assets/8d8e958d-8aee-4626-a428-ecbd64917f51" />


<img width="343" alt="10-User-Created" src="https://github.com/user-attachments/assets/bc2978b9-f7f4-477f-8583-f6e030f7f4a5" />

**IT**: `Bob Marley` `Isaac Spencer` `William Kent`

<img width="422" alt="11-IT-Users" src="https://github.com/user-attachments/assets/8c45d0e4-4946-466c-a7ff-4f1ae80de7a1" />



- **Sales**: `John Burke`, `Bridget Hance`, `Taiwo Jake`

<img width="490" alt="12-Sales Employees" src="https://github.com/user-attachments/assets/e47d118d-58e0-4efd-9113-cb2593dffb07" />


- **Finance**: `Frank James`, `Freddy Hammy`, `Friday Ince`


---<img width="476" alt="13-Sales Employees" src="https://github.com/user-attachments/assets/730c2241-b219-4925-a884-b0c8a20db78b" />


### 4. 👥 Create Security Groups
- Right-click the domain → `New > Group`

<img width="538" alt="01-Create A Security Group " src="https://github.com/user-attachments/assets/2ffa31d7-f8f9-422f-857c-c288186b43db" />

  
  - `IT_Dept`
<img width="346" alt="IT _Dept" src="https://github.com/user-attachments/assets/10f499f0-d913-44e7-a30d-a8ed944b31bf" />

    
  - `Sales_Dept`
<img width="350" alt="04-Sales_Sec_Grp" src="https://github.com/user-attachments/assets/32f17e6a-a755-45ea-9962-d3a5013ee607" />

- `Finance_Dept`
<img width="362" alt="02-Finance_Sec_Grp" src="https://github.com/user-attachments/assets/b0acf84e-bf5a-42f6-950b-61203fcb2bca" />

- `All Security Groups Created`
<img width="560" alt="05-Sec_Grp_Created" src="https://github.com/user-attachments/assets/83e7d889-9f41-437e-801f-378719977dcd" />


- Add users to their respective department groups

<img width="774" alt="06-Add_Fin_Users" src="https://github.com/user-attachments/assets/d4026dd5-1a0b-49a6-a95e-d794db647c5c" />

<img width="364" alt="07-Add to Finance" src="https://github.com/user-attachments/assets/b9cac340-aa88-4d2f-9400-73700bbf9669" />

<img width="715" alt="08-Add Users to IT" src="https://github.com/user-attachments/assets/356fc6b9-fdd4-411b-bc51-606e1232cd84" />

<img width="786" alt="09-Add-Users to Sales" src="https://github.com/user-attachments/assets/e7d091ec-51ac-41da-9429-f5da3c3810e3" />

---

### 5. 📁 Create Departmental Folders and Set NTFS Permissions
- On the server or shared storage:
  - Create folders: `IT`, `Sales`, `Finance`
 
    <img width="799" alt="10-Folders" src="https://github.com/user-attachments/assets/9c4f1584-a512-46b6-83a8-739656713f72" />

- Set NTFS Permissions:
  - Each group gets **Full Control** on its folder

- Properties
<img width="860" alt="11-Finance-properties" src="https://github.com/user-attachments/assets/2999e8d2-ca8b-46d9-9d06-fa6ffe8098b0" />

- Security Settings
<img width="811" alt="12-Finance-Security Setting" src="https://github.com/user-attachments/assets/bf7cf0e0-8a55-42c1-bbc7-3b26c54e984b" />

- Permissions
<img width="289" alt="13-Finance Permission" src="https://github.com/user-attachments/assets/061e2497-a73f-4eb5-9f12-1d6399890863" />

- Add Target Group
<img width="391" alt="14-Add fininace_dept" src="https://github.com/user-attachments/assets/9370ab2c-6744-4d3d-859d-4f26488f562a" />

- Full Control Checked
<img width="292" alt="15-Finance Full control" src="https://github.com/user-attachments/assets/419e5e62-7ceb-4742-9bdb-8b3a728be210" />

- Full Control Completed: `Finance`
<img width="298" alt="16-Finance- Full Control Activation " src="https://github.com/user-attachments/assets/c496eba9-4337-4cdf-a1b1-fc0fa630aaca" />

- Full Control Completed: `IT`
<img width="296" alt="17-IT - Full Control" src="https://github.com/user-attachments/assets/a05d5ccc-de65-42bf-811e-d200d3986818" />

- Full Control Completed: `Sales`
<img width="290" alt="18-Sales Full Control" src="https://github.com/user-attachments/assets/2d46b6ae-a976-4f6e-9a21-7269ffaef1f6" />


  - `ITManager` **Bob Marley** gets **Read/List** access to `Sales` and `Finance`

- `Bob Marley ` permission in Finance
<img width="297" alt="19 Bob on Finance " src="https://github.com/user-attachments/assets/4232b0de-88b4-47da-b8a9-e0b1d645fb50" />

- `Bob Marley ` permission in Sales
<img width="312" alt="20 - Bob on Sales" src="https://github.com/user-attachments/assets/0bb6ba0b-430c-4025-9fab-bf1e3a2bd7b5" />

---

### 6. 🔗 Share the Folders Over the Network
- Go to folder properties → `Sharing` tab
![Uploading 21-properties.png…]()

<img width="413" alt="22-Sharing TAB" src="https://github.com/user-attachments/assets/557b7643-0b86-4d7d-b9b2-9338a5cf578b" />

- Enable **Advanced Sharing**
<img width="355" alt="23- Advanced Sharing" src="https://github.com/user-attachments/assets/8467536a-af8b-44d2-8fa8-48a945317fd3" />

  
- Set **Share Permissions** matching NTFS rules
<img width="314" alt="24- Apply Sharing " src="https://github.com/user-attachments/assets/d1713f33-9cdc-4e21-91c7-3156eb2e385c" />


<img width="319" alt="25-Network Path" src="https://github.com/user-attachments/assets/ce760db2-6840-4394-88e3-f4367155b709" />

---

### 7. 🛠️ Create and Configure GPOs (Group Policy Objects)

| Department (OU) | GPO Name      | Policies Included |
|------------------|---------------|--------------------|
| IT               | `IT_GPO`      | Enable CMD & PowerShell |
| Sales            | `Sales_GPO`   | Block Control Panel & App Installations |
| Finance          | `Finance_GPO` | Enforce Strong Passwords & Lockouts |

#### Steps:
1. Open **Group Policy Management Console (GPMC)** (`gpmc.msc`)
<img width="1262" alt="01-GPO" src="https://github.com/user-attachments/assets/ecb2287b-3831-4a88-8d67-6dd056b147af" />


2. Right-click `Group Policy Objects` → `New`
3. Create:<img width="933" alt="02-Create GPO and Link" src="https://github.com/user-attachments/assets/e65d36d0-7fbf-476d-b59c-adefc5cacd64" />

   - `IT_GPO`, `Sales_GPO`, `Finance_GPO`
     <img width="298" alt="04_All GPOs" src="https://github.com/user-attachments/assets/cfb60c29-814a-4d11-9182-0b7f89b9d7f0" />

4. Right-click each GPO → `Edit`:
   - IT:
     - `User Config > System`: Enable Command Prompt
     - 
     - `Windows Components > PowerShell`: Enable PowerShell
   - Sales:
     - `User Config > Control Panel`: Restrict access
     - `Windows Installer`: Disable installations
   - Finance:
     - `Computer Config > Security Settings > Password Policy`: 
       - Minimum length: 12
       - Complexity: Enabled
       - Lockout threshold: 3 invalid attempts
6. Link each GPO to its respective OU

---

### 8. 🔍 Test and Verify
- Login as sample users to confirm:
  - GPOs applied correctly
  - Folder access permissions work as expected
  - ITManager can access Sales and Finance folders

---

## 🏁 Conclusion

This lab simulates a departmental infrastructure within Active Directory, covering user and group management, security permissions, and Group Policy design. It mimics tasks performed by system administrators in real corporate environments and serves as an excellent foundation for Active Directory mastery.

---

## 📄 Author

**Your Name Here**  
Student | IT Professional | Cybersecurity Enthusiast  
[LinkedIn](#) | [GitHub](#) | [Blog](#)

---

