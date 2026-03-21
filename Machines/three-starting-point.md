# Three

## My Takeaways

- **DNS Sub-Domain Enumeration:** A DNS server stores different types of records about its configuration. For example, an A record translates a domain name into an IPv4 address. Subdomains are the way to organize your pages/content in a single domain, so you can find different services running in them, making them a valuble during reconnaissance.

- **How to interact with AWS Services:** To interact with an AWS service you need to go through its API. There are different ways to do this, in this case we used AWS CLI to communicate with S3.

- **Reverse Shell:** You make the target connect back to your machine, spawning a shell that gives you remote control over it, instead you connecting to the target, the target connects to you.

## 🔍 Reconnaissance

We start we a simple nmap scan.

- Open Ports: 22 (SSH), 80 (HTTP)

## 🛠️ Path to Intrusion

- **Vulnerability Detected:** After the scan I decided to start with the low-hanging fruit. In this case inspecting the webpage and its source code. I found out a `.php` file, which tell us the server is running PHP. I also found an email address within the same domain, which give us a clue to search more about this domain/subdomains.

- **Explotation:**
  - We use Gobuster to enumerate subdomains and found this subdomain pointing to an AWS S3 bucket.

  - Using AWS CLI to interact with the bucket, I listed its content, and confirmed this bucket was the web server root, so if we can get access to this bucket we can control how the web page interacts with us.

  - We uploaded a simple PHP webshell using the `system()` function, which allowed us to pass commands through URL query parameters.

  - then a one-liner reverse shell was made, a simple bash script, hosted it on a local python HTTP server and used the web shell to make the target fetch the script via `curl` and pipe it into `bash`, triggering the connection back to our machine.

  - Once the target connected back, we have access to the server.

- **Obstacles:**
  - I had to learn how to interact with the AWS S3 service through the CLI before being able to enumerate and write to the bucket.

## Why does it works

- It is crucial to understand the systems behind an application so we know what vulnerabilities can be present. In this case, there was a S3 bucket publicly exposed with no authentication or authorization controls, allowing us to list and upload files without restriction. The web application also lacked input validation, so we could pass arbitrary commands through query parameters.

- Without proper access controls and input sanitization, we were able to make the server spawn a shell on our machine This highlights how a single misconfiguration, an open S3 bucket combined with a lack of input validation can lead to full remote code execution.
