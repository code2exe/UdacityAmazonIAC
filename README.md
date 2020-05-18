# UdacityAmazonIAC
A Cloud Formation Script to automate deployment of infrastructure for a high-availability Udagram web app

## Architecture Diagram (LucidChart)
<img src="https://github.com/code2exe/UdacityAmazonIAC/blob/master/Udagram%20Architecture.png" width="100%">

### Steps to deploy (as I did on Windows Powershell):

Ensure you have aws cli installed on your machine (Use your preferred search engine for that)

First, deploy network stack:

`.\create.bat $stackname udagram-net.yml udagram-net-params.json`   (NB: You should choose a stackname of your choice)

Then, deploy bastion host stack:

`.\create.bat $stackname udagram-bastion.yml udagram-bastion-params.json`

Finally, deploy server stack:

`.\create.bat $stackname udagram-server.yml udagram-server-params.json`



Made changes and want to redeploy any of the stacks?

`.\update.bat $stackname $yaml.yml $params.json`