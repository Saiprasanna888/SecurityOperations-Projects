## **Step 1: Install Active Directory Domain Services (AD DS)**

1. Log in to your **Windows Server** with administrative privileges.
2. Open **Server Manager** (automatically opens on login).
3. Click **Manage → Add Roles and Features**.
4. In the wizard:

   * **Role-based or feature-based installation** → Next
   * Select your **server** → Next
   * Under **Server Roles**, check **Active Directory Domain Services** → Next
   * Click **Add Features** if prompted
   * Continue through the wizard → **Install**
5. Wait for installation to complete.

---

## **Step 2: Promote Windows Server to Domain Controller**

1. After installation, in **Server Manager**, you will see a notification flag → click **Promote this server to a domain controller**.
2. In the **Deployment Configuration** wizard:

   * Select **Add a new forest**
   * Enter your **Root domain name**, e.g., `corp.local`
3. Set **Domain Controller Options**:

   * Forest and Domain functional level → **Windows Server 2016 or higher**
   * Check **DNS server** and **Global Catalog** → Next
   * Set **Directory Services Restore Mode (DSRM) password** → Next
4. Review **DNS Options** (default is fine) → Next
5. Review **Paths** (default C:\Windows\NTDS etc.) → Next
6. Review **Prerequisites Check** → if all pass → **Install**
7. The server will automatically **reboot** after promotion.

---

## **Step 3: Verify Domain Controller**

1. Log back into the server after reboot.
2. Open **PowerShell** or **Command Prompt**:

   ```powershell
   systeminfo
   ```

   * Check that the **Domain** is listed as `corp.local` (or your domain name).
3. Open **Active Directory Users and Computers (ADUC)** from the Start menu to confirm AD installation.

---

## **Step 4: Create Users in Active Directory**

1. Open **Active Directory Users and Computers (ADUC)**.
2. Navigate to your domain → Right-click **Users** → **New → User**
3. Enter:

   * First Name
   * Last Name
   * User logon name (e.g., `saiprasanna`)
4. Set **password** and configure:

   * User must change password at next login → Optional
   * User cannot change password → Optional
   * Password never expires → Optional
5. Click **Finish**.
6. Repeat for additional users as needed.

---

## **Step 5: Join Client Machine to Domain (Optional)**

1. On a Windows client machine, open **System Properties → Change Settings → Change…**
2. Select **Domain**, enter your AD domain name → OK
3. Provide **Domain Admin credentials**
4. Restart client machine to apply changes.

---

## **Step 6: Verify Users and Logins**

1. Log in with a newly created user on the client machine.
2. Ensure you can access domain resources (shared folders, printers).
3. Document the user accounts and take screenshots for your repo.
