# pmg-kesl-integration
Script for integrate Kaspersky Endpoint Security (Linux) as antivirus engine in Proxmox Mail Gateway

Required steps

1. Install Kaspersky Endpoint Security (Linux) on Proxmox Mail Gateway host

2. Turn off all KESL tasks related to persistent protection

3. Enable mail and archives scan in KESL for on-demand scan and set action for infected files to skip:

<pre>kesl-control --set-settings 3 FirstAction=skip
kesl-control --set-settings 3 ScanMailBases=yes
kesl-control --set-settings 3 ScanPlainMail=yes
kesl-control --set-settings 3 ScanArchived=yes
kesl-control --set-settings 3 ScanSfxArchived=yes</pre>

4. Copy script pmg-custom-check to /usr/local/bin directory
