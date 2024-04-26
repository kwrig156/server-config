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

  Rules for IP Tables
  <img width="1280" alt="Screenshot 2024-04-15 at 12 38 54 PM" src="https://github.com/kwrig156/server-config/assets/165214775/49baa50e-e4fa-42fa-a08c-0cc480b21e4c">

I opted to disable UFW and enable IP Tables on the Ubuntu server instead because IP Tables provides finer control over network traffic and offers advanced security features that align with the specific requirements of my environment. Utilization of IP Tables allows for custom firewall rules to precisely define which types of traffic are allowed or blocked, enabling a more tailored and robust security posture. 

The rules I chose to implement on this machine demonstrate a proactive approach to security, prioritizing the use of secure protocols and services while rejecting insecure ones. For instance, I disabled insecure protocols or services and enabled their secure counterparts. One example is ensuring that SMTPS (SMTP over TLS/SSL) is enabled while SMTP (plain text SMTP) is disabled. This ensures that sensitive email communications are encrypted, providing stronger protection against eavesdropping and interception.

Additionally, I configured IP Tables to allow only necessary incoming and outgoing traffic, restricting access to services and ports based on their intended use and security considerations. This helps minimize the attack surface and reduces the risk of unauthorized access or exploitation of vulnerabilities.
