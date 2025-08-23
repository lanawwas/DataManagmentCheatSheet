### Update and install build essential and software propertites common
sudo apt update && sudo apt dist-upgrade -y
sudo apt install build-essential
sudo apt install software-properties-common

### Hardene ssh setting with pub/private key authentication 

sudo vim /etc/ssh/sshd.config
ssh-keygen -t rsa -b 4096

https://linuxize.com/post/how-to-install-virtualbox-guest-additions-in-ubuntu/
sudo adduser lanawwas vboxsf

On local add the public key to remote 

ssh-copy-id -i ~/.ssh/id_rsa.pub remoteUser@remoteIP -pSSHPort

OR

cat ~/.ssh/id_rsa.pub | ssh remoteUser@remoteIP -psSShPort 'cat >> ~/.ssh/authorized_keys'

On remote after copying rsa.pub key of the local machine to remote by scp, you can add the identiy to the remote authrised

https://www.ssh.com/academy/ssh/copy-id
https://phoenixnap.com/kb/setup-passwordless-ssh

ssh-copy-id -i /path/to/key/file user@host.com

After add more security to ssh: 

https://phoenixnap.com/kb/ssh-to-connect-to-remote-server-linux-or-windows

https://phoenixnap.com/kb/linux-ssh-security

https://linuxhandbook.com/ssh-hardening-tips/

Change the congiuration in etc/ssh/sshd_config :
1. Change default port number. 
2. Use SSH key pairs for authentication
3. Disable password-based logins
4.Disable root access to your server and use a regular account with the

1. Authentication

text
# Disable password authentication (ensure key-based authentication is working first)
PasswordAuthentication no
ChallengeResponseAuthentication no
UsePAM no

# Enable public key authentication
PubkeyAuthentication yes

2. Root Access

text
# Never allow root SSH login
PermitRootLogin no

3. Limit Access

text
# Restrict user SSH access
AllowUsers your_admin_user
# or to a group:
# AllowGroups sshusers

4. Login/Brute Force Mitigation

text
# Limit number of authentication attempts
MaxAuthTries 3

# Disconnect idle sessions
ClientAliveInterval 300
ClientAliveCountMax 2

5. Network and Port

6. Forwarding and Extras

text
# Disable X11 forwarding (unless you require it)
X11Forwarding no

7. Cryptography: Use Strong Algorithms

Add these for ciphers and key exchange:

text
Ciphers chacha20-poly1305@openssh.com,aes256-gcm@openssh.com,aes128-gcm@openssh.com,aes256-ctr,aes192-ctr,aes128-ctr
MACs hmac-sha2-512-etm@openssh.com,hmac-sha2-256-etm@openssh.com,umac-128-etm@openssh.com
KexAlgorithms curve25519-sha256@libssh.org,diffie-hellman-group-exchange-sha256

8. Logging

    Increase log level for better monitoring:

text
LogLevel VERBOSE

9. Advanced/Optional

    Implement Two-Factor Authentication (2FA) via PAM

    Use Fail2Ban to block brute-force attempts



Install fail2ban

Installation

    Update the System:
    Begin by updating your system to ensure you have the latest package listings.

    bash
    sudo apt update && sudo apt upgrade

Install Fail2ban:
Install Fail2ban using the package manager.

bash
sudo apt install fail2ban

Start and Enable Fail2ban:
Start the Fail2ban service and enable it to start on boot.

bash
sudo systemctl start fail2ban
sudo systemctl enable fail2ban

Configuration

    Copy Default Configuration:
    Copy the default configuration file to create a local configuration file that you can modify.

    bash
    sudo cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local

Edit Local Configuration:
Open the jail.local file in a text editor to configure Fail2ban settings.

bash
sudo nano /etc/fail2ban/jail.local

Basic Settings:

    ignoreip: Specify IP addresses that should never be banned (e.g., your own IP).

    text
    ignoreip = 127.0.0.1/8 ::1

bantime: Set the duration for which an IP is banned (e.g., 1 day).

text
bantime = 1d

findtime: Specify the time window for counting failed login attempts.

text
findtime = 600

maxretry: Set the number of allowed failed attempts before banning.

text
maxretry = 3

Configure Jails:
Ensure the SSH jail is enabled to protect against unauthorized SSH access.

text
[sshd]
enabled = true
port = ssh
logpath = %(sshd_log)s
backend = %(sshd_backend)s

Email Notifications (Optional):
If you have a mail service configured, set up email notifications for banned IPs.

text
destemail = your-email@example.com
action = %(action_mw)s

Restart Fail2ban:
After making changes, restart the Fail2ban service to apply the new configuration.

bash
sudo systemctl restart fail2ban

Verification

    Check Fail2ban Status:
    Verify that Fail2ban is running correctly.

    bash
    sudo systemctl status fail2ban

Check iptables Rules:
Review the iptables rules to ensure Fail2ban has added the necessary rules.

bash
sudo iptables -L

https://linuxhandbook.com/fail2ban-basic/

-------------------
Install and configure to install stable update automaticlly 
sudo apt install -y unattended-upgrades
sudo dpkg-reconfigure --priority=low unattended-upgrades

--------------------

UFU settings to allow cusotm port for ssh after enable

https://www.digitalocean.com/community/tutorials/how-to-set-up-a-firewall-with-ufw-on-ubuntu-18-04


Adding Swap : https://linuxize.com/post/how-to-add-swap-space-on-ubuntu-18-04/

Install JDK and Oracle JDK: https://linoxide.com/install-java-ubuntu-20-04/
