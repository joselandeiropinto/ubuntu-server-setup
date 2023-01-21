# Install FTP Server (vsftpd)
____

- Install FTP server
    `sudo apt install vsftpd`
- Configure firewall to allow trafic
    `sudo ufw allow 20/tcp`
    `sudo ufw allow 21/tcp`
    `sudo ufw allow 900/tcp`
    `sudo ufw allow 4000:5000/tcp`
    `sudo ufw reload`
- Use Filezila or WinSCP to connect to the FTP server, you can log in with your system user