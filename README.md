# Managing User Accounts and Template Account Utilization
## Description
This project showcases the management of various objects within an Active Directory (AD) environment, focusing on user account creation, group management, and the use of templates to streamline user provisioning. Additionally, it demonstrates the use of advanced AD tools like the Active Directory Administrative Center (ADAC) and integration of PowerShell for automating tasks and capturing commands executed through the ADAC interface.

## Tools and Utilities

- **Windows Server 2016**: Primary server hosting the Active Directory Domain Services (AD DS).
- **Active Directory Users and Computers (ADUC)**: Interface for managing user and computer accounts.
- **Active Directory Administrative Center (ADAC)**: Enhanced tool for managing AD objects with a modern UI.
- **Server Manager**: Central hub for accessing AD tools and managing server roles.

## Environments

### Server Environment
- **Operating System**: Windows Server 2016 configured with AD DS.
- **AD Structure**: Set up with user containers and groups to manage organizational units (OUs).

## User Account Management

### Standard User Creation
- Created users within **ADUC** in the Users container.
- Configured accounts with options such as password change enforcement at first logon for enhanced security.
- Demonstrated management options including adding users to groups, resetting passwords, and enabling/disabling accounts.

### Template User Accounts
- Created a template user account (e.g., `_SalesUser`) for quick replication during onboarding.
- Template accounts were configured with default group memberships and necessary settings for standardization.
- Showed how to create new users by copying the template account to inherit group memberships and permissions efficiently.

## Program Walkthrough

### Managing User Accounts
1. **User Creation in ADUC**: Created a user within the Users container and configured password change at first logon.
2. **Group Management**: Illustrated how to add users to groups, reset passwords, and enable/disable user accounts.

### Using Template Accounts
1. **Template Account Creation**: Set up a template user (`_SalesUser`) to simplify onboarding.
2. **New User Creation**: Demonstrated copying the template account to streamline new user setup while inheriting default permissions.

### Advanced Management with ADAC
1. **Accessing ADAC**: Navigated through **Server Manager** to open ADAC.
2. **User Creation**: Used ADAC for detailed user account creation with property and group assignment configurations.
3. **Membership Management**: Demonstrated removing users from groups and managing memberships.
4. **PowerShell History Viewer**: Captured PowerShell commands used within ADAC for reuse and automation.

### PowerShell Command Automation
- Captured PowerShell commands from ADAC and documented them for script building.
- Used PowerShell scripts for batch processing and repetitive administrative tasks to streamline workflows.

### Applying Filters and Criteria
- Utilized ADAC filters to search for users with specific attributes (e.g., expired passwords).
- Demonstrated how applying filters aids in maintaining user account security and policy compliance.

# Managing Active Directory Objects

## Managing User Accounts

1. In **Active Directory Users and Computers** under the **Users** container, create a new user. Ensure the check box for **User must change password at next logon** is checked.
   -  **Account is Disabled -** Normally when user will be out of office for an extended amount of time, so no one tries to authenticate while they’re away
   -  **Password Never Expired -** Not common to use as passwords should always change after a given amount of time
   -  **User cannot change password** - Not usually selected because instances may occur where a user may feel the need to change their password

![image](https://github.com/user-attachments/assets/c196d32e-804d-4ec9-bb9d-56619722e2bc)

![image 1](https://github.com/user-attachments/assets/174d6f25-431a-45f6-9880-486fca3c01c1)

![image 2](https://github.com/user-attachments/assets/638dab8a-469c-4227-90c2-9a7280814fa3)

2. There are various options that can be done with user accounts: Add to a group, Disable, Reset password,
![image 3](https://github.com/user-attachments/assets/aa45575c-c97b-4f01-b90c-797f340367b3)


3. **Reset Password** - In the case user forgets password and needs it changed, it can be done. If they locked themselves out. check the **Unlock the user’s account** box

![image 4](https://github.com/user-attachments/assets/2e504652-12b9-49e4-a3da-41b8f2c9308a)

### Template Account

1. In **Active Directory Users and Computers** under the **Users** container, create a new user. Make sure to check boxes for **password change at next logon** and **account is disabled**

![image 5](https://github.com/user-attachments/assets/1c227c84-f428-48a3-9bd1-d1a169a00269)

2. The reason the name begins with an **underscore** is because alphabetically and numerically, the name will above all user names. Also, common knowledge that an account beginning with an underscore is a **template account**

![image 6](https://github.com/user-attachments/assets/6416bcae-2b2d-4d8d-b4f2-25d2aed7c2b5)

3. Right-click the **_SalesUser** and select **Properties. I**n the **Member of tab** it will show that the template is a member of **domain users**
   -  Any new user created will automatically be assigned to **Domain Users** group by default

![image 7](https://github.com/user-attachments/assets/5e22befb-24fb-4ac7-8b94-bdea74f1fb49)

4. Select **Add** and add the user to the **Sales User** group. _SalesUser will now be apart of the **Sales User** group

![image 8](https://github.com/user-attachments/assets/8d077d17-92ba-4388-bbdf-bb4800d9fa61)

![image 9](https://github.com/user-attachments/assets/c0ebc024-916c-45e4-abc2-c5bf6d434fd8)

5. Anytime a user is hired for the Sales department, create a template from the _SalesUser User. Right-click **_SalesUser →** select **Copy. Copy Object - User** page will be brought up to input new users information from the template

![image 10](https://github.com/user-attachments/assets/8c42c767-6bf8-473f-abc3-27db4057ed06)

![image 11](https://github.com/user-attachments/assets/62a3abce-5485-4fb3-a81a-fca29c311f35)

![image 12](https://github.com/user-attachments/assets/5ccda76c-e9db-4876-b45d-94ec8b7f8e2f)

6. Check the properties of the new user and select **Member Of.** Can see that the new user was automatically assigned to **Sales User** group because a user template was used
   -  Using a template helps reduce admin mistakes and speeds up processes

![image 13](https://github.com/user-attachments/assets/aea3e7c7-ed52-4542-baba-14ea85ee0b9a)

### Active Directory Administrative Center

Managing objects using ADAC

1. Navigate to Server Manager → Tools → Active Directory Administrative Center. Select the domain currently using and navigate to the **Users** container

![image 14](https://github.com/user-attachments/assets/249b6fbe-5198-43b5-9365-42998ed36663)

![image 15](https://github.com/user-attachments/assets/1353204a-c899-428b-b375-7495dd82172c)

2. New users can be created in ADAC as well. Select **New → User.** It is more extensive and can provide details about users as well as add them to groups

![image 16](https://github.com/user-attachments/assets/ad783f88-32fc-446d-ab04-efddac27abf4)

![image 17](https://github.com/user-attachments/assets/9ff5e73d-f49e-4bd2-b374-80656efc9524)

3. Navigate to a user already created and select **Member of** and select remove the user from the **Sales User** group

![image 18](https://github.com/user-attachments/assets/56debd58-ffea-43ee-abd0-236116b7d306)

4. In ADAC at the bottom is the **Windows Powershell History.** Windows Server provides a built-in PowerShell History Viewer, allowing you to see the PowerShell commands executed behind the scenes when performing actions in the graphical interface. 
   -  Can select the command ran, copy it to a text file and can later use it in PowerShell scripts

![image 19](https://github.com/user-attachments/assets/f9b7cc62-89b8-479d-bc7a-23d33f999160)

![image 20](https://github.com/user-attachments/assets/b5945347-aac8-4c5f-8e42-876c62d2d3fc)

5. Under **Add criteria,** filters can be applied to identify specifications of a given user such as **users with an expired password**

## Summary
This project provided a comprehensive overview of AD object management, user provisioning using templates, and task automation using PowerShell, enhancing both efficiency and security within the AD environment.

