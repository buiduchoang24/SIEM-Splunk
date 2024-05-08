# Splunk

## Splunk Enterprise Server
- I use Ubuntu Server 22.04 for this.
- Use this command line to get splunk from its download page<br>
```bash
wget -O splunk-9.2.1-78803f08aabb-linux-2.6-amd64.deb
"https://download.splunk.com/products/splunk/releases/9.2.1/linux/splunk-9.2.1-78803f08aabb-linux-2.6-amd64.deb"
```
- After that, you will have a .deb file at the path where you have just entered command line, use this to run<br>
```bash
sudo dpkg -i splunk_package_name.deb
```
- Then, use this to start splunk
```bash
sudo /opt/splunk/bin/splunk start --accept-license
```
- And you will have some command lines like this
![image](https://github.com/buiduchoang24/Splunk/assets/166605385/9dbb629c-6473-48fb-a8d1-355101327325)
- Use a machine that has the same ip address of Ubuntu Server to run Web UI

## Splunk Universal Forwarder
