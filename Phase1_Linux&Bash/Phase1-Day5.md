# Phase1-Day5

## Key takeaways
- SSH is a network protocol that lets you securely ocnnect to and control a remote computer over an unsecured network.It encrypts all traffic between your workstation and the server.
- SSH runs over TCP (predominately on port 22), ensuring reliable delivery of data packets.
- It utilizes public key cryptography to authenticate both the client and the server. Each side holds a key pair (private and public), and they verify each other before any sensitive data is exchanged.
- Once identities are confirmed, SSH negotiates a shared, symmetric key for fast encryption for the rest of the session.
- SSH allows for **Remote command execution**, run shell commands on a server as if you were sitting at its console.
- **Secure File Transfer**, safely transfer files using SFTP or SCP, which are ran over the SSH connection.
- **Port Forwarding (Tunneling)** SSH tunneling allows you to forward traffic from one network port to another, allowing secure access to services behind firewalls.

## Tasks completed
- Installed terraform via Ubuntu WSL environment