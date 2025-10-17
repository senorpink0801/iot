# AWS Laboratory Procedures

## Experiment 1: Develop Application Using Platform as a Service

**Date:** 12/10/08  
**Lab Date:** 10/9/25

### Aim
To develop an application using a platform as a service.

### Procedure

#### A) Launching a Free Tier Windows Instance and Logging in via Remote Desktop

1. Go to the EC2 service and click "Launch Instance"
2. To launch an instance sized to select free tier only, under the "pricing" section
3. Choose a free tier eligible instance type like "t2.micro"
4. Keep the default settings for "Configure Instance Details"
5. You can choose up to 60 MB of free storage on your instance
6. If your don't have a key pair already, create a new one with "RSA" key type. It's used for secure login
7. Launch the instance and go to "Instance" and look for "Get Windows password" option. It's company and used for free login
8. On local machine, use remote desktop communication client on document Microsoft Remote Desktop
9. Open remote desktop client and enter the public DNS of Windows instance when you can find in EC2 console instance details
10. Use administrator, username and temporary password
11. You may be prompted to choose an authentication method, select "use a different account" and browse to your private key
12. Once authenticated, you'll be connected to your Windows EC2 instance

#### B) Launching a Linux Instance and Accessing via SSH

1. Go to EC2 Service in AWS Console and "Launch Instance"
2. Choose free tier eligible instance
3. Open terminal
4. Use SSH command

**Replacing `/username` with default username for your chosen AMI and `/public-DNS` with `/public-dns` of your Linux instance:**

```bash
ssh -i /path-to-our-private-key-file.pem /username@ /public-dns
```

5. When prompted, enter passphrase. Set keypair
6. If it is successful, you will be logged in

---

## Experiment 2: Develop Application Implementing Infrastructure as a Service

**Date:** 18/10/08  
**Lab Date:** 3/9/25

### Aim
To develop an application implementing infrastructure as a service.

### Procedure

#### A) Sign In to Your AWS Account
- Go to the EC2 Service
- Click on "Create bucket"

#### B) Choose a Unique Bucket Name
- Select a region closest to your user

#### C) Under "Block public access settings" it is generally recommended to keep all settings disabled unless you have specific security requirements

#### D) Upload an Image

**In S3 Console, select the newly created bucket:**
1. Drag and drop your image file into upload area or click "Add files" to browse and select it
2. Make the upload image file
3. Click on the "Actions" menu
4. Choose "Make public"

#### E) Implement File Versioning on the S3 Bucket

**To Enable File Versioning:**
1. In S3 console, select your bucket
2. Click on properties tab
3. Under "versioning", click on "Enable"
4. Choose "new version" (keep existing versioning configuration)
5. Click the save
6. Whenever you upload a new version of the same file S3 will remain previous version

#### F) Host a Static Website on S3 Bucket

**To Enable Static Website Hosting:**
1. Click on properties tab under static website hosting, click on Edit

**To Get the Public Access Level:**
1. Go to bucket → "permission" tab
2. Under public access settings for object S3-t and list access to grant public read access
3. Click on "Save"

---

## Experiment 3: Develop Application Using Software as a Service

**Date:** 19/10/16  
**Lab Date:** 3/19/25

### Aim
To deploy an application using software as a service.

### Procedure

**If your www file is not already in an S3 bucket, upload it to an S3 bucket. Follow these steps:**

1. Now you need to create a Lambda function. Follow these steps:
   - Go to AWS Lambda Service
   - Click "Create function"

2. Choose python as author your function from scratch, give your function a name, choose runtime and click "Create function"

3. Write a simple Lambda function to return the HTML content

**In code.py, you can use the module to read HTML file from S3 and return it as response:**

4. You need to ground your Lambda function permission to "read" www file from S3 and return it as a response

5. Create the rest API and test event and select these as policies and create an event

6. For example: Leave default options, world option

   a) An event, JSON option value

---

## Experiment 4: Send Data Between an IoT Client and Server Using Cooja Simulator

**Date:** 23/10/31  
**Lab Date:** 22/8/25

### Aim
To perform data transfer between an IoT client and server using Cooja simulator.

### Procedure

1. Open the system in Ubuntu OS and open the terminal

2. Execute the following commands to open the Cooja simulator console page:
   ```bash
   => su root
   => password
   => cd contiki-2.7
   => cd tools
   => cd cooja
   => ant run
   ```

3. Once the above commands are executed, the simulator console page is been opened

4. Go to file option, select "New Simulator" and click on the "Create" button

5. To create server node, go to node, select "Add node" and "Create new node start" and choose the data file that to be transferred to client

6. Add note number and positioning of the note

**Simultaneously create the client motor node to of node can be n**

---

## Additional Notes

**Once all the require nodes are created link on the start button in simulation control area to start the data transfer.**

After some time in same app right side click on the server node #06 !

In the note tool, select the collected wire

In collect view there will be various analysis factor of the node, such as node control sensor mcp network graph power node information etc...

Note down the graph reading simply by information the graph for other topologies and draw the instant graph.

---

## Cost Summary Table

| Service | Cost (₹) |
|---------|----------|
| OBS (20) | ✓ |
| COE (30) | ✓ |
| IaaS (10) | ✓ |
| **Total (60)** | **✓** |