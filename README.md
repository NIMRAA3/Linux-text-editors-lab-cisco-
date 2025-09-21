# Cybersecurity Lab – Working with Text Files in the CLI

## 🎯 Objectives
In this lab, I explored Linux text editors and configuration files. The objectives were:  
- Learn to use graphical text editors.  
- Practice with command-line editors.  
- Edit and manage configuration files for system services.  


## 📝 Part 1: Graphical Text Editors  

### Step 1: Open SciTE from the GUI  
- Logged in as user **analyst** (password: `cyberops`).  
- Opened **SciTE**:  
  `Applications > CyberOPS > SciTE`  
- Created and saved `space.txt` in `/home/analyst`.  

**Q:** Could you immediately find `space.txt` in the SciTE file dialog?  
**A:** No. SciTE only shows known extensions. Select **All Files (*)** to view `.txt`.  

### Step 2: Open SciTE from the Terminal  
```bash
scite space.txt
Prompt disappeared because the terminal was busy running SciTE.

Closed SciTE with CTRL+C.

Q: Why was the prompt not shown in the terminal?
A: Because the terminal was running SciTE until it was stopped.

## 📝 Part 2: Command Line Text Editors 

Opened space.txt with nano:

nano space.txt


Text looked truncated (single long line).

Navigated with Home/End.

Q: What character does nano use to represent wrapped lines?
A: The > or $ symbol, depending on nano version.

Exited nano with CTRL+X.

## 📝 Part 3: Working with Configuration Files

Step 1: User vs System Config Files
cat .bashrc


User configs live in /home/analyst.

System-wide configs live in /etc.

Q: Why not store user configs in /etc?
A: Regular users don’t have write permissions in /etc.

 Step 2: Editing .bashrc

Changed color code in prompt:

32 (green) → 31 (red) using SciTE.

Opened a new terminal → prompt showed red.

Q: Did the already-open terminal change color?
A: No. .bashrc runs only on new shell sessions.

Edited again with nano → 33 (yellow).

Reloaded with:

bash


Prompt turned yellow. ✅

 Step 3: Editing nginx Configuration

Opened file:

sudo nano -l /etc/nginx/custom_server.conf


Changed settings:

Port → listen 8080;

Root → /usr/share/nginx/html/text_ed_lab/

Restarted nginx:

sudo nginx -c custom_server.conf


Opened Firefox → 127.0.0.1:8080 showed nginx page.

Q: What was the error message?
A: A missing favicon.ico file (non-critical).

Stopped nginx:

sudo pkill nginx


Reloading page failed, confirming nginx was stopped.

⚡ Challenge Question

Q: Can you edit the /etc/nginx/custom_configuration.conf file with SciTE?
A: Yes. Run:

sudo scite /etc/nginx/custom_configuration.conf


This opens the file in SciTE with root permissions. Save changes and reload nginx with:

sudo nginx -s reload

📌 Reflection

Learned differences between graphical editors (SciTE) and CLI editors (nano).

Understood user vs system configuration storage.

Edited .bashrc and nginx config files successfully.

Practiced service management (stop/restart nginx).

Gained hands-on experience with permissions and text editing in Linux.
