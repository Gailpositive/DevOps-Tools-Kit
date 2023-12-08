=====================================================================
Get started with openSSh

===================================================================
1. Get-WindowsCapability -Online | Where-Object Name -like 'OpenSSH*'


2. Name  : OpenSSH.Client~~~~0.0.1.0
State : NotPresent

Name  : OpenSSH.Server~~~~0.0.1.0
State : NotPresent


3. ### Start the sshd service
Start-Service sshd

### OPTIONAL but recommended:
Set-Service -Name sshd -StartupType 'Automatic'

### Confirm the Firewall rule is configured. It should be created automatically by setup. Run the following to verify
if (!(Get-NetFirewallRule -Name "OpenSSH-Server-In-TCP" -ErrorAction SilentlyContinue | Select-Object Name, Enabled)) {
    Write-Output "Firewall Rule 'OpenSSH-Server-In-TCP' does not exist, creating it..."
    New-NetFirewallRule -Name 'OpenSSH-Server-In-TCP' -DisplayName 'OpenSSH Server (sshd)' -Enabled True -Direction Inbound -Protocol TCP -Action Allow -LocalPort 22
} else {
    Write-Output "Firewall rule 'OpenSSH-Server-In-TCP' has been created and exists."
}
=====================================================================================================================================================

ABOUT KEY PAIRS
============================================================
1. ssh-keygen -t ed25519

2. Generating public/private ed25519 key pair.

3. Enter file in which to save the key (C:\Users\username/.ssh/id_ed25519):
Get-Service ssh-agent | Set-Service -StartupType Automatic

4. Start-Service ssh-agent

5. Get-Service ssh-agent
6. cd downloads
7. ls *.pem (to view all pem)
8. Open AWS instance
9. ssh-add (key pem){2048 SHA256:MeIkE/N41jNWCsc3oroOXj06tQGNv36CeskG92eWpOs new-Jenkins.pem (RSA)}
========================================================================

https://learn.microsoft.com/en-us/windows-server/administration/openssh/openssh_keymanagement
https://learn.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse?tabs=powershell
