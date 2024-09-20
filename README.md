To perform the tasks you’ve mentioned, here's the step-by-step guide for each:
1. **OpenVAS Scan on Metasploitable VM and Export as PDF
   
Steps:
   - **Install OpenVAS (Greenbone Vulnerability Manager):**
     ```bash
     sudo apt update
     sudo apt install openvas
     sudo gvm-setup
     sudo gvm-start
     ```
     Configure and Access the OpenVAS Web UI
     - Open a browser and go to `https://localhost:9392`.
     - Log in using the admin credentials created during the setup.
     - Ensure Metasploitable VM is running and reachable from the OpenVAS machine.
   
   - **Add Metasploitable VM as a Target:**
     - Go to "Configuration" > "Targets" > "Create New Target."
     - Set the target IP to the Metasploitable VM IP.

   - **Launch a Scan:**
     - Go to "Scans" > "Tasks" > "Create New Task."
     - Select the target, configure scan options, and launch the scan.

   - **Download Report as PDF:**
     - Once the scan is complete, navigate to the "Scans" > "Reports" section.
     - Select the scan, choose the "Export" option, and export the report as a PDF.

### 2. **Generate an HTML Nikto Report for Metasploitable VM**

#### Steps:
   - **Install Nikto:
     
     sudo apt install nikto
     ```
   - **Run the Nikto Scan:
     
     nikto -h <Metasploitable_VM_IP> -o output.html -Format htm
     ```
   - This will save the output as `output.html`, which you can then view in any browser.

### 3. **Grab the Banner for a Metasploitable VM Port Using Netcat and Save the Screenshot**

#### Steps:
   - **Use Netcat to Grab the Banner:
     
     nc <Metasploitable_VM_IP> <Port_Number>
     ```
     Replace `<Metasploitable_VM_IP>` with the IP of the Metasploitable VM and `<Port_Number>` with a specific port like 21 (FTP) or 80 (HTTP).
   - **Example Command for Port 21 (FTP)
     
     nc <Metasploitable_VM_IP> 21
     ```
     This will return the banner information for the FTP service.

   - Take a Screenshot
     Use a screenshot tool on your system (such as `gnome-screenshot` or `flameshot` on Linux) to capture the terminal output.
   
   For automation, use a tool like `import` (ImageMagick) to capture a screenshot of a specific window:
   
   import -window root banner_screenshot.png
   ```

