# OpenVPN Client Installation and Setup on Linux

A quick, production-ready guide to installing the **OpenVPN client** and connecting via an `.ovpn` configuration file across major Linux distributions.

## 1. Install the OpenVPN Package

Open your terminal and run the command corresponding to your Linux distribution:

### Ubuntu / Debian / Linux Mint
```bash
sudo apt update && sudo apt install openvpn -y
```

### Fedora / RHEL / CentOS
```bash
sudo dnf install openvpn -y
```

### Arch Linux / Manjaro
```bash
sudo pacman -S openvpn --noconfirm
```

---

## 2. Establish the VPN Connection

Download or move your `.ovpn` configuration file to your machine. Navigate to the directory containing the file and run:

```bash
sudo openvpn --config client.ovpn
```
> [!NOTE]
> Closing the terminal window or pressing `Ctrl + C` terminates the VPN session. To run the connection in the background as a background process, append the `--daemon` flag:
> `sudo openvpn --config client.ovpn --daemon`

---

## 3. Automate Username and Password Authentication (Optional)

To bypass typing your credentials manually every time you connect, you can securely store them:

1. Create a dedicated credentials file:
   ```bash
   sudo nano /etc/openvpn/credentials
   ```
2. Add your **username** on the first line and your **password** on the second line, then save and exit:
   ```text
   your_username
   your_password

   I usually prefer something recognizable and short such as 'kaan'.
   ```
3. Restrict file permissions so only the root user can read it:
   ```bash
   sudo chmod 600 /etc/openvpn/credentials
   ```
4. Open your `.ovpn` configuration file in a text editor, locate the `auth-user-pass` directive, and update it to point to your credentials file:
   ```text
   auth-user-pass /etc/openvpn/credentials
   ```

Running `sudo openvpn --config client.ovpn` will now authenticate automatically.

> [!IMPORTANT]
> I personally use Arch Linux with KDE Plasma interface. You can use whatever you want for your cyber security sessions. The selection of distributions have no effect whatsoever with your progress. I can clearly recommend Arch for further administration.


