![Alt text](relative/path/to/image.jpg)
Domain: Identity & Access Management

Objective: Master Active Directory (AD) to manage users, groups, policies, and security configuration in a Windows enterprise environment.

Key Outcomes: 

- Create Organizational Units (OUs) and user accounts.
- Configure domain-level and OU-level Group Policies.
- Enforce security policies (password complexity, access control

Lab Setup

Topology:

Windows Server: 192.168.1.10

Domain: [campus.edu](http://campus.edu/)    

![image.png](attachment:f71eb6fc-fdff-4569-9ad6-c29d677d2d51:image.png)

Tools used: 

- Active Directory Users & Computers (**`dsa.msc`**)
- Group Policy Management Console
- Command Prompt (**`net user`**, **`gpupdate`**)

Lab Tasks

# **Task 1: Create Organizational Units & User Accounts**

1. Open **`Active Directory Users and Computers`** via **`dsa.msc`**.
2. Right-click domain (**`campus.edu`**) → **New → Organizational Unit**.
    - Name: **`Minecraft`** (example OU).
3. Create users inside **`Minecraft`** OU:
    - Right-click OU → **New → User**.
    - Usernames: **`creeper`**, **`zombie`**, **`steve`**.
    - Password: **`P@ssw0rd`** (uncheck *"User must change password at next logon"*).

**Why This Matters:**

> OUs mirror organizational structure (e.g., Finance, IT). Policies applied to an OU affect all contained objects.
> 
1. Open **`Active Directory Users and Computers`** via **`dsa.msc`**.

![image.png](attachment:29b79ce3-846a-4d2a-8163-23103100e79a:image.png)

1. Right-click domain (**`campus.edu`**) → **New → Organizational Unit**.
    - Name: **`Minecraft`** (example OU).

![image.png](attachment:27f0fcdb-de53-4e50-bb29-a0fd8f52a0ce:image.png)

![image.png](attachment:9f8bd055-94d8-4a32-ac18-30a498f107af:image.png)

1. Create users inside **`Minecraft`** OU:
    - Right-click OU → **New → User**.
    - Usernames: **`creeper`**, **`zombie`**, **`steve`**.
    - Password: **`P@ssw0rd`** (uncheck *"User must change password at next logon"*).

![image.png](attachment:1e12d79c-0c75-4a21-a48d-ead46af3fb9b:image.png)

![image.png](attachment:4d0c9aaa-2daf-438f-b0ae-1750b30e198c:image.png)

![Screenshot 2025-06-05 112548.png](attachment:a8cfae74-9917-4349-b649-51b5805b4923:Screenshot_2025-06-05_112548.png)

![image.png](attachment:e5f937cd-8dee-45f2-a46d-de5f176928ce:image.png)

# Task 2: **Configure domain-level and OU-level Group Policies**

### **Task 2: Set Domain-Level Password Policy**

1. Open **Group Policy Management** → Expand **`Forest: campus.edu`** → **Domains** → **`campus.edu`**.

![image.png](attachment:e647b418-f7fe-447c-ac65-a062b5b123f7:image.png)

1. Edit **Default Domain Policy**.

![image.png](attachment:6ec3d326-672f-4375-a421-106a7beacdf5:image.png)

1. Navigate to:
    
    **`Computer Configuration → Policies → Security Settings → Account Policies → Password Policy`**.
    
    ![image.png](attachment:80a70e96-628e-4816-ba97-aa8dbba310f6:image.png)
    
2. Set **Minimum password length** to **`10 characters`**

![image.png](attachment:2c36f43e-e9bc-44e1-9c37-c208c43df205:image.png)

![image.png](attachment:e47e4cd3-e46a-4336-a699-d751c3044f49:image.png)

Now we need to refresh the group policy in the Command Prompt 

![image.png](attachment:81e4d2b4-ac1c-4e73-9675-a96da509b373:image.png)

**Security Impact:**

> Domain-level policies enforce baseline security (e.g., password complexity) across all users.
>
