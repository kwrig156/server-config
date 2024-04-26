# server-config
Configuration and Hardening of Ubuntu and Windows Servers
<img width="1278" alt="Screenshot 2024-04-15 at 12 38 25 PM" src="https://github.com/kwrig156/server-config/assets/165214775/6b8476dc-19c3-4866-a01f-30c633436464">
The file '/etc/ssh/sshd_config', represents the main configuration file for SSH on Ubuntu 20.04. In this project, I configured SSH utilizing OpenSSH on the Linux server. To secure the SSH service, I implemented the following hardening techniques: 

1. PermitRootLogin:

Disabled remote root login by setting PermitRootLogin to "no". This prevents direct root access via SSH, enhancing security by requiring users to log in with individual accounts and then use sudo for administrative tasks.

2. Password Authentication:

Disabled password authentication by setting PasswordAuthentication to "no", enforcing the use of SSH key-based authentication. This method is more secure than passwords and helps mitigate brute-force attacks.

3. Protocol and Cipher Configuration:

Configured SSH protocol version and allowed ciphers to ensure compatibility with modern security standards, while mitigating vulnerabilities associated with older protocols and weak encryption algorithms.

4. Other Security Measures

- Enabled UsePAM and UseDNS directives for additional security checks and DNS resolution.
- Set LoginGraceTime to a lower value to reduce the window for potential attacks.
- Disabled EmptyPassword to enforce password requirements for user accounts.
- Configured Banner to display a warning message to users upon SSH login, notifying them of unauthorized access attempts and potential legal consequences.
