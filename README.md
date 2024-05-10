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
- Use another machine that has the same ip address of Ubuntu Server to run Web UI, it will show like this
![image](https://github.com/buiduchoang24/Splunk/assets/166605385/59851436-dd32-4e16-82ae-2c3920282b33)


## Splunk Universal Forwarder
- First of all, when you run a download file, you will encounter this, please choose **An on-premises Splunk Enterprise instance** and Next <br>
![image](https://github.com/buiduchoang24/Splunk/assets/166605385/612a29f3-8b58-416d-8a06-9449314f76e2)
- Then, give the username and password<br>
![image](https://github.com/buiduchoang24/Splunk/assets/166605385/7c51cea7-283f-4708-aea3-5194c113799d)
- You will need to supply either Deployment Server IP or Indexer IP<br>
![image](https://github.com/buiduchoang24/Splunk/assets/166605385/b67c63a9-8860-416a-ad4d-47a1e72c7a8a)
- Finally, click Install and wait it for finishing>br>
![image](https://github.com/buiduchoang24/Splunk/assets/166605385/30c436d8-87e8-4bf4-b469-40ee7de8f484)
- You can check whether your Splunk Forwarder is running or not by observing in Services or services.msc
![image](https://github.com/buiduchoang24/Splunk/assets/166605385/5165d113-6284-4783-a5a7-145cf5f9c0e0)
- Or using this powershell script to 
```powershell
Test-NetConnection -Computername <IP_Address> -port <Port>
```
![image](https://github.com/buiduchoang24/Splunk/assets/166605385/32f4eaa7-2c2a-4606-a9f2-3954548851d4)






