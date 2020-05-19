# UdacityAmazonIAC
A Cloud Formation Script to automate deployment of infrastructure for a high-availability Udagram web app

## Architecture Diagram (LucidChart)
<img src="https://github.com/code2exe/UdacityAmazonIAC/blob/master/Udagram%20Architecture.png" width="100%">

### Steps to deploy (as I did on Windows Powershell):

Ensure you have aws cli installed on your machine (Use your preferred search engine for the how-to)

First, sign into your AWS Console and create an EC2 Key Pair and an S3 Bucket (In my case, I named them both udagram and udakey as in my bastion script). 

Then, upload the key pair (Ensure the names are properly encoded into the bastion script as it is necessary for it to work) 

Now, let's deploy network stack:

`.\create.bat $stackname udagram-net.yml udagram-net-params.json`   (NB: You should choose a stackname of your choice)

Then, we deploy the bastion host stack:

`.\create.bat $stackname udagram-bastion.yml udagram-bastion-params.json`

Finally, we deploy the server stack:

`.\create.bat $stackname udagram-server.yml udagram-server-params.json`



Made changes and want to redeploy any of the stacks? Simply run:

`.\update.bat $stackname $yaml.yml $params.json`