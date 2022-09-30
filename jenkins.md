In All nodes:

/ect/netplan/.... .yaml
dhcp: false

# Let NetworkManager manage all devices on this system
network:
  version: 2
  renderer: NetworkManager
  ethernets:
    enp0s3:
      dhcp4: false
      addresses: [10.0.0.162/24]
      routes:
      - to: default
      nameservers:
        addresses: [8.8.8.8,8.8.4.4]



netplan apply

On master:
-------------------
sudo -i
sudo apt update
sudo apt install openjdk-11-jdk -y
Check the java version now: java -version
Add the repository key to the system:
 wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
Append the Debian package repository address to the server’s sources.list:
 sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
Run update: sudo apt update

curl -fsSL https://pkg.jenkins.io/debian/jenkins.io.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null

echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null

sudo apt-get update

sudo apt-get install jenkins

sudo systemctl status jenkins

sudo systemctl enable jenkins

sudo systemctl start jenkins

Copy the slave node's public key[id_rsa.pub] to Master Node's known_hosts file

```
mkdir -p /var/lib/jenkins/.ssh
cd /var/lib/jenkins/.ssh
ssh-keyscan -H SLAVE-NODE-IP-OR-HOSTNAME >>/var/lib/jenkins/.ssh/known_hosts
# ssh-keyscan -H 172.31.38.42 >>/var/lib/jenkins/.ssh/known_hosts
chown jenkins:jenkins known_hosts
chmod 700 known_hosts
```

On slave
-------------------
sudo -i
sudo apt update
sudo apt install openjdk-11-jdk -y
Check the java version now: java -version

```
# Create user and add the user to wheel group
useradd jenkins-slave-01
# Create SSH Keys
sudo su - jenkins-slave-01
ssh-keygen -t rsa -N "" -f /home/jenkins-slave-01/.ssh/id_rsa
# The private and public keys will be created at these locations `/home/jenkins-slave-01/.ssh/id_rsa` and `/home/jenkins-slave-01/.ssh/id_rsa.pub`
cd .ssh
cat id_rsa.pub > authorized_keys
chmod 700 authorized_keys

```

<img width="514" alt="image" src="https://user-images.githubusercontent.com/103237142/193164135-f485199e-042b-40ff-9a2a-fed6908c4520.png">


For slave node- in manage node:

run on slave node : `$ more id_rsa`

<img width="444" alt="image" src="https://user-images.githubusercontent.com/103237142/193165009-1df69c7f-54d3-4c40-8ee7-98aad1992843.png">

<img width="459" alt="image" src="https://user-images.githubusercontent.com/103237142/193165022-bfed3d79-643f-4458-8356-062b3d553168.png">

