# ☁️ AWS Cloud Computing Experiments (IaaS, PaaS, Storage, DBaaS)

---

## 🔷 Experiment 1: IaaS (Windows Virtual Machine in AWS EC2)

### Aim:

To create and connect a Windows Virtual Machine using AWS EC2.

### Steps:

1. Login to AWS Console
2. Go to **Services → EC2**
3. Click **Launch Instance**
4. Enter Name: `Windows-VM`
5. Select **Windows Server (AMI)**
6. Choose Instance Type: `t2.micro`
7. Create Key Pair and download `.pem` file
8. Configure Security Group:

   * Allow **RDP (Port 3389)**
9. Click **Launch Instance**

### Connect:

1. Select Instance → Click **Connect**
2. Choose **RDP Client**
3. Download RDP file
4. Get password using key pair
5. Login

### Result:

Windows Virtual Machine created and accessed successfully.

---

## 🔷 Experiment 2: IaaS (Linux Virtual Machine in AWS EC2)

### Aim:

To create and connect a Linux Virtual Machine.

### Steps:

1. Go to EC2 → Launch Instance
2. Enter Name: `Linux-VM`
3. Select **Amazon Linux / Ubuntu AMI**
4. Choose Instance Type: `t2.micro`
5. Create Key Pair
6. Allow **SSH (Port 22)**
7. Launch Instance

### Connect:

```bash
ssh -i key.pem ec2-user@<public-ip>
```

### Result:

Linux Virtual Machine successfully created and connected.

---

## 🔷 Experiment 3: PaaS (Deploy Web Application)

### Aim:

To deploy a web application on AWS EC2.

### Steps:

1. Launch Linux EC2 instance
2. Connect using SSH
3. Install web server:

```bash
sudo yum update -y
sudo yum install httpd -y
```

4. Start server:

```bash
sudo systemctl start httpd
sudo systemctl enable httpd
```

5. Navigate to directory:

```bash
cd /var/www/html
```

6. Create webpage:

```bash
sudo nano index.html
```

7. Add:

```html
<h1>Hello AWS</h1>
```

8. Save file
9. Open browser → Enter Public IP

### Result:

Web application successfully deployed.

---

## 🔷 Experiment 4: Storage as a Service (AWS S3 Bucket)

### Aim:

To create S3 bucket and upload files.

### Steps:

1. Go to **S3 Service**
2. Click **Create Bucket**
3. Enter unique bucket name
4. Select Region
5. Click **Create Bucket**

### Upload:

1. Open Bucket
2. Click **Upload**
3. Select files → Upload

### Result:

Files successfully stored in S3 bucket.

---

## 🔷 Experiment 5: S3 Versioning

### Aim:

To enable versioning in S3.

### Steps:

1. Open S3 Bucket
2. Go to **Properties**
3. Enable **Versioning**

### Test:

1. Upload file
2. Upload same file again
3. Check Versions tab

### Result:

Multiple versions of files maintained.

---

## 🔷 Experiment 6: VirtualBox (Local VM)

### Aim:

To create virtual machine using VirtualBox.

### Steps:

1. Install VirtualBox
2. Click **New**
3. Enter Name and OS type
4. Select ISO file
5. Allocate RAM (≥2GB)
6. Create Virtual Disk
7. Click **Start**

### Result:

Local virtual machine successfully created.

---

## 🔷 Experiment 7: DBaaS (DynamoDB)

### Aim:

To create NoSQL database using DynamoDB.

### Steps:

1. Go to **DynamoDB**
2. Click **Create Table**
3. Enter:

   * Table Name: `Employee`
   * Primary Key: `EmpID`
4. Click **Create Table**

### Insert Data:

1. Open Table → Explore Items
2. Click **Create Item**
3. Add:

```json
{
  "EmpID": 101,
  "Name": "Jayesh",
  "Dept": "IT"
}
```

4. Save

### Result:

Data successfully inserted in DynamoDB.

---

## ⚠️ Important Note:

* Always terminate EC2 instances after use to avoid charges
* EC2 setup involves launching, configuring, connecting, and terminating instances ([Amazon Web Services, Inc.][1])

---

## 🎯 Conclusion:

All AWS cloud services (IaaS, PaaS, Storage, DBaaS) were successfully implemented using AWS platform.

---

[1]: https://aws.amazon.com/ec2/getting-started/?utm_source=chatgpt.com "Getting Started with Amazon EC2"
