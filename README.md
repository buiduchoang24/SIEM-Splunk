# Splunk

- This is my overall model<br>
![Untitled Diagram drawio (2)](https://github.com/buiduchoang24/Splunk/assets/166605385/23652eda-5dd1-4e6f-a036-45419ca04b0b)


## Set up Splunk Server and Forwarder

### Splunk Enterprise Server
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
- Go to Settings -> Forwading and Receiving -> Configure receiving
![image](https://github.com/buiduchoang24/Splunk/assets/166605385/0e9c09ae-c25e-4e3f-9cc6-56d82f5269bb)
- Add port 9997, and in Universal Forwarder Setup, session Receiving Indexers, you must set port to 9997 too
![image](https://github.com/buiduchoang24/Splunk/assets/166605385/df86ce9f-1abf-40f9-9d40-61b0b2db6252)


### Splunk Universal Forwarder
- First of all, when you run a download file, you will encounter this, please choose **An on-premises Splunk Enterprise instance** and Next <br>
![image](https://github.com/buiduchoang24/Splunk/assets/166605385/612a29f3-8b58-416d-8a06-9449314f76e2)
- Then, give the username and password<br>
![image](https://github.com/buiduchoang24/Splunk/assets/166605385/7c51cea7-283f-4708-aea3-5194c113799d)
- You will need to supply either Deployment Server IP or Indexer IP<br>
![image](https://github.com/buiduchoang24/Splunk/assets/166605385/b67c63a9-8860-416a-ad4d-47a1e72c7a8a)
- Finally, click Install and wait it for finishing<br>
![image](https://github.com/buiduchoang24/Splunk/assets/166605385/30c436d8-87e8-4bf4-b469-40ee7de8f484)
- You can check whether your Splunk Forwarder is running or not by observing in Services or services.msc
![image](https://github.com/buiduchoang24/Splunk/assets/166605385/5165d113-6284-4783-a5a7-145cf5f9c0e0)
- Or using this powershell script to 
```powershell
Test-NetConnection -Computername <IP_Address> -port <Port>
```
![image](https://github.com/buiduchoang24/Splunk/assets/166605385/32f4eaa7-2c2a-4606-a9f2-3954548851d4)
- Go to Settings -> Forwarder Management, you should see your Universal Forwarder here
![image](https://github.com/buiduchoang24/Splunk/assets/166605385/6ff06a6d-5ec2-4562-8bfc-b1d35980c44a)

## Add data to Splunk

### Add Data from Forwarder
- In Web GUI, go to Settings -> Add Data, at here, you can see three methods where you can get data from
![image](https://github.com/buiduchoang24/Splunk/assets/166605385/5922f123-2187-4ef2-9f31-359fbaf437ee)
- I will get data from Forwarder first, so I click into it
- It makes me select the forwarder<br>
![image](https://github.com/buiduchoang24/Splunk/assets/166605385/94d1cb82-530c-41f4-b52c-98fa9369a103)
- After I press Next, it has many options for me to choose
![image](https://github.com/buiduchoang24/Splunk/assets/166605385/b9683a76-81bf-424e-a675-e29fd490dacc)
- And I choose Window Event Log to monitor
![image](https://github.com/buiduchoang24/Splunk/assets/166605385/0f805a58-14fc-48a5-afbf-2e3830c0a823)
- Review what I chose<br>
![image](https://github.com/buiduchoang24/Splunk/assets/166605385/e54cc06f-5930-4109-a108-f98a4fc2448b)

### Add Data from Upload file
- Here, I have a dataset from LetDefend
![image](https://github.com/buiduchoang24/Splunk/assets/166605385/f931a38e-161d-4846-84b1-565cb8bf8c81)
- And I will upload it to Splunk by following steps, first is choose Upload
![image](https://github.com/buiduchoang24/Splunk/assets/166605385/93af93b3-65bb-49e1-8067-e310e408864a)
- Select sources, choose tutorial dataset, then Next, waiting for uploading and Start searching
![image](https://github.com/buiduchoang24/Splunk/assets/166605385/0b0096e8-c6b6-48e8-92e4-b12adf4d2051)
- You will see the interface like this<br>
![image](https://github.com/buiduchoang24/Splunk/assets/166605385/f8adc518-2a49-430d-b8a0-6a97dd0abd1a)













