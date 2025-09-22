# Lab Report: Working with Text Files in the CLI

## Objectives
- Gain familiarity with Linux command line text editors.  
- Work with graphical and command line-based text editors.  
- Understand and modify configuration files in Linux.  

## Required Resources
- Security Workstation Virtual Machine (VM).  

## Lab Tasks

### Part 1: Graphical Text Editors
- Explored SciTE, the graphical text editor available in the CyberOps VM.  
- Created and saved a text file (`space.txt`) in the user’s home directory.  
- Identified that SciTE does not display `.txt` files by default and learned to show all files.  
- Opened SciTE both via GUI and command line using `scite space.txt`.  

**Observation:** When launched from CLI, the prompt disappears because the terminal is running SciTE.  



### Part 2: Command Line Text Editors
- Opened `space.txt` using **nano**:  
  ```bash
  nano space.txt
````

* Navigated through the file using arrow keys, Home/End, and Page Up/Page Down.
* Identified that nano uses the **> or \$ symbol** to show line continuation.
* Learned save (`CTRL+O`), exit (`CTRL+X`), search (`CTRL+W`), and help (`CTRL+G`) commands.



### Part 3: Working with Configuration Files

1. **Locating Configuration Files**

   * Used `ls -la` to view hidden files in the home directory.
   * Opened `.bashrc` and identified configurations like prompt color and aliases.
   * Verified `/etc` directory contains system-wide configuration files.

   **Answer:** User-specific configs are in the home directory because regular users lack write permissions for `/etc`.

2. **Editing User Configurations**

   * Edited `.bashrc` in SciTE to change prompt color (green → red → yellow).
   * Confirmed changes apply only to new terminal windows.

3. **Editing Service Configurations**

   * Opened nginx config `/etc/nginx/custom_server.conf` with nano:

     ```bash
     sudo nano -l /etc/nginx/custom_server.conf
     ```
   * Changed listening port from 81 → 8080.
   * Changed root directory to `/usr/share/nginx/html/text_ed_lab/`.
   * Restarted nginx with modified config.
   * Verified local web server at `127.0.0.1:8080`.

   **Error Observed:** Missing `favicon.ico` file triggered a warning.

   * Stopped nginx using:

     ```bash
     sudo pkill nginx
     ```

   **Answer:** After shutdown, the webpage no longer loads.

4. **Challenge Question**

   * Used SciTE with root permissions to edit configs:

     ```bash
     sudo scite /etc/nginx/custom_configuration.conf
     ```
   * Saved and reloaded service with:

     ```bash
     sudo nginx -s reload
     ```



## Reflection

* Learned differences between **graphical** and **command line editors**.
* Explored **user vs system-wide configuration files**.
* Reinforced importance of permissions in Linux.
* Understood that changes often require **service restart/reload** to take effect.

[click here](https://github.com/NIMRAA3/Linux-text-editors-lab-cisco-/blob/main/66.jpg)








