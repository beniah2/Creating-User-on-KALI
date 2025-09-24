## 1. Onboarding a New Staff Member

**Story:**  
Our cyber security firm just hired a new staff member named David. As part of the on-boarding process, the IT team needs to create a new user account for him on our Kali Linux system so he can log in and begin work.

**Action:**  
We create a new user account with a home directory for David.

**Command:**
sudo adduser david

- `adduser` creates the user directory, sets up a password, and configures default files.
    
- `sudo` ensures you’re running with administrative rights.


![Image 1](<Pasted image 20250924172608.png>)


---

## **2. Assigning David a Password**

**Story:**  
As part of on-boarding, David needs a secure password to log in.

**Action:** Set password for the new user.

**Command:**
sudo passwd david {This command prompts you to enter and confirm the password}

![Image 3](<Pasted image 20250924173116.png>)

---

## **3. Elevating David’s Privileges (Promotion)**

**Story:**  
After a few months, David is promoted to **Team Lead** and needs administrative rights to install and configure tools.

**Action:** Add David to the `sudo` group.

**Command:**
sudo usermod -aG sudo david

- `usermod` modifies user accounts.
    
- `-aG sudo` adds the user to the `sudo` group without removing existing groups.

**Verification Command:**
groups david

![Image 2](<Pasted image 20250924173747.png>)

---

## **4. Revoking Privileges (Resignation)**

**Story:**  
David has resigned, and for security, you must revoke his administrative rights before full removal.

**Action:** Remove David from the `sudo` group.

**Command:**
sudo deluser david sudo {This ensures he no longer has elevated priviledges}

**Verification Command:**
groups david

![Image 5](<Pasted image 20250924174504.png>)

---
## **5. Deleting David’s Account**

**Story:**  
Finally, HR confirms David’s exit. To maintain security hygiene, you delete his user account and all associated files.

**Action:** Remove David’s account and home directory.

**Command:**
sudo deluser --remove-home david {`--remove-home` deletes his home directory}

![Image 4](<Pasted image 20250924174959.png>)

---
### **Conclusion**

Through this scenario, I've demonstrated how to:

- **Create** a new user for on-boarding.
    
- **Assign & manage passwords**.
    
- **Grant elevated privileges** (promotion).
    
- **Revoke privileges** (resignation).
    
- **Delete user accounts securely**.
