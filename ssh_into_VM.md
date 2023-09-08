# **HOW TO SSH INTO YOUR VM AND UPLOAD TO GITHUB**

## **How to SSH Into Your VM**

### Prerequisites:
* SSH client installed on your host machine (e.g., OpenSSH on Linux/Mac or PuTTY on Windows).
* A running VM with an operating system that has an SSH server installed (e.g., `sshd` for Linux).
* Network connectivity between the host machine and the VM.

### Steps:
#### 1. VM Network Settings:
* Ensure that your VM network setting is either in 'Bridged' mode (so it gets an IP address directly from your network) or 'Host-Only' (where it can communicate only with the host machine). The choice depends on your need and security considerations.

#### 2. Find the VM's IP Address:
* Log into the VM.
* Depending on your OS, retrieve the VM's IP address. On most Linux distributions, you can use:

```
ip addr show
```

Look for an IP address like `192.168.x.x` or `10.x.x.x`.

#### 3. Ensure SSH Server is Running:
* If you're using Linux, the SSH server is often named `sshd`. Check if it's running with:

```
sudo service ssh status
```

If it's not running, start it with:

```
sudo service ssh start
```

#### 4. Connect from the Host Machine:
* Open a terminal or command prompt on your host machine.
* Use the SSH command followed by the VM's IP address. For instance:

```
ssh username@VM_IP_ADDRESS
```

Replace `username` with a valid user on the VM and `VM_IP_ADDRESS` with the IP address you found in step 2.

#### 5. First Connection Security Check:
* If this is your first time connecting to the VM, you will likely see a message regarding the authenticity of the host. If you trust the connection, type **'yes'** and then enter the password for the **'username'** when prompted.

#### 6. Successful Connection:
* Once connected, you will be presented with the VM's shell prompt, indicating you're now operating inside the VM.

#### 7. End the SSH Session:
* To end the session and return to your host machine, simply type:

```
exit
```

##### Optional:
* To improve security, consider setting up SSH key-based authentication instead of using passwords.
* If you're going to be accessing the VM regularly, consider giving it a static IP address or setting up a hostname for easier access.

