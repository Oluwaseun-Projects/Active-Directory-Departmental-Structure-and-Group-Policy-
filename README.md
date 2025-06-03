# 🛡️ Active Directory Departmental Structure & Group Policy Project

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
  - `IT_Dept`
  - `Sales_Dept`
  - `Finance_Dept`
- Add users to their respective department groups

---

### 5. 📁 Create Departmental Folders and Set NTFS Permissions
- On the server or shared storage:
  - Create folders: `IT`, `Sales`, `Finance`
- Set NTFS Permissions:
  - Each group gets **Full Control** on its folder
  - `ITManager` gets **Read/Write or Full Control** access to `Sales` and `Finance`

---

### 6. 🔗 Share the Folders Over the Network
- Go to folder properties → `Sharing` tab
- Enable **Advanced Sharing**
- Set **Share Permissions** matching NTFS rules

---

### 7. 🛠️ Create and Configure GPOs (Group Policy Objects)

| Department (OU) | GPO Name      | Policies Included |
|------------------|---------------|--------------------|
| IT               | `IT_GPO`      | Enable CMD & PowerShell |
| Sales            | `Sales_GPO`   | Block Control Panel & App Installations |
| Finance          | `Finance_GPO` | Enforce Strong Passwords & Lockouts |

#### Steps:
1. Open **Group Policy Management Console (GPMC)** (`gpmc.msc`)
2. Right-click `Group Policy Objects` → `New`
3. Create:
   - `IT_GPO`, `Sales_GPO`, `Finance_GPO`
4. Right-click each GPO → `Edit`:
   - IT:
     - `User Config > System`: Enable Command Prompt
     - `Windows Components > PowerShell`: Enable PowerShell
   - Sales:
     - `User Config > Control Panel`: Restrict access
     - `Windows Installer`: Disable installations
   - Finance:
     - `Computer Config > Security Settings > Password Policy`: 
       - Minimum length: 12
       - Complexity: Enabled
       - Lockout threshold: 3 invalid attempts
5. Link each GPO to its respective OU

---

### 8. 🔍 Test and Verify
- Login as sample users to confirm:
  - GPOs applied correctly
  - Folder access permissions work as expected
  - ITManager can access Sales and Finance folders

---

## 📌 Optional Enhancements

- 📁 Map folders via Group Policy Preferences
- 📈 Enable audit logs for access tracking
- 🧪 Automate user/group creation with PowerShell scripts

---

## 🏁 Conclusion

This lab simulates a departmental infrastructure within Active Directory, covering user and group management, security permissions, and Group Policy design. It mimics tasks performed by system administrators in real corporate environments and serves as an excellent foundation for Active Directory mastery.

---

## 📄 Author

**Your Name Here**  
Student | IT Professional | Cybersecurity Enthusiast  
[LinkedIn](#) | [GitHub](#) | [Blog](#)

---

