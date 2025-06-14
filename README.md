# squid-server

Squid is a widely used, open-source caching and forwarding proxy server that supports HTTP, HTTPS, and FTP protocols. It optimizes bandwidth, enhances response times by caching frequently accessed content, and provides robust access control mechanisms.

This is a step-by-step guide to deploy a Squid proxy server on an Ubuntu EC2 instance in a public subnet on Amazon Web Services (AWS) and configure a Windows Server in a private subnet to route its internet traffic through the 
proxy. It includes instructions for using a whitelist file to restrict access to specific domains, ensuring secure and controlled internet access.

# Architecture Overview

The setup involves:

1. Squid Proxy Server: An Ubuntu EC2 instance in a public subnet, running Squid to handle HTTP/HTTPS traffic and enforce domain-based access control using a whitelist.

2. Windows Server: An EC2 instance in a private subnet, configured to route internet traffic through the Squid proxy.

3. AWS VPC Configuration: A public subnet with internet access and a private subnet with outbound access via a NAT Gateway or the Squid proxy instance.

4. Security Groups: Rules to allow traffic between the Windows Server, Squid proxy, and the internet.

5. Whitelist: A whitelist.txt file to restrict access to approved domains.

The Windows Server will use the Squid proxy’s private IP and port (default: 3128) to access whitelisted internet resources, ensuring no direct internet access from the private subnet.

The lab is broken into four parts: (AWS, Squid-configuration, Windows-configuration, and troubleshooting(if necessary)) by referencing the following files:

1. aws-config.txt
2. squid-config.txt
3. windows-config.txt
4. Troubleshooting.txt