# 04 DNS

## why is it important to have a DNS server in our local environment?

- As a company grows, sharing resources through the local network becomes easier with domain names or subdomain like `accounting.local` instead than having to remember IP addresses.

- A local DNS server also gives you control over outbound traffic. Since all DNS queries have to go through it, you can inspect requests and block users from reaching malicious domains.

- It also helps with network segmentation through a concept called DNS Views, this allows you to serve different DNS responses to different parts of your network, preventing internal divisions from interfering with each other.

- A local DNS server may seem like added complexity, but when properly administered it becomes a control point that helps enforce security policies and meet compliance requirements.
