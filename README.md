### EC2 Challenge Assignment

**Objective:**
Students will gain hands-on experience launching, configuring, and accessing an Amazon EC2 instance for the first time. This challenge will build foundational AWS skills essential for cloud operations.

---

### Walkthrough Phase

**Step 1: Launch an EC2 Instance**
1. Navigate to the AWS Management Console.
2. Go to the EC2 dashboard.
3. Click on **Launch Instance**.
4. Choose the **Amazon Linux 2 AMI** (Free Tier eligible).
5. Select the instance type **t2.micro** (Free Tier eligible).
6. Click **Next** through the default configurations until the **Key Pair** section.

**Step 2: Create a Key Pair**
1. Under the Key Pair section:
   - Click **Create new key pair**.
   - Name the key pair your username (e.g., `john_doe_keypair`).
   - Choose **RSA** and file format as **.pem**.
   - Click **Create key pair** and download the key.
2. Save the `.pem` file securely (e.g., on your desktop).

**Step 3: Configure Security Groups**
1. You will be presented with a pre-defined security group using name `student-default-sg-<username>`:
   - **Task:** Configure a rule to allow inbound traffic on port 22.

**Step 4: Add Tags**
1. Under the **Add Tags** section:
   - Add the following key-value pairs:
     - Key: `Name`
       - Value: Your username (e.g., `john_doe`).
     - Key: `Owner`
       - Value: Your username (e.g., `john_doe`).

**Step 5: Launch the Instance**
1. Review your configurations.
2. Click **Launch Instance**.

**Step 6: Identify Interesting Information**
1. Once the instance is running, locate the following information from the instance details:
   - Public IP Address
   - Instance ID
   - Availability Zone

**Step 7: Connect to the Instance**
1. Open a terminal on your local machine.
2. Change permissions of the `.pem` file using:
   ```bash
   chmod 400 john_doe_keypair.pem
   ```
3. SSH into the instance:
   ```bash
   ssh -i john_doe_keypair.pem ec2-user@<Public_IP_Address>
   ```
4. Verify successful login.

---

### Challenge Phase

**Scenario:**
Launch, configure, and access an EC2 instance independently, using the skills learned during the walkthrough.

#### Task Instructions:
1. **Launch an EC2 Instance**
   - Choose the same configuration as in the walkthrough (Amazon Linux 2, t2.micro).
   - Tag the instance with the following key-value pairs:
     - Key: `Name`
       - Value: Your username.
     - Key: `Owner`
       - Value: Your username.
   - Select a security group that allows SSH access (port 22).

2. **Create and Use a Key Pair**
   - Create a new key pair with your username.
   - Download the `.pem` file and use it to access the instance.

3. **Document Interesting Information**
   - Record the instance’s Public IP, Instance ID, and Availability Zone.

4. **Connect to the Instance**
   - Log in via SSH using your key pair.

**Bonus Challenge:**
- Use the terminal to:
  - Update the instance’s package manager:
    ```bash
    sudo yum update -y
    ```
  - Create a simple file named `welcome.txt` in the home directory with a welcome message.

