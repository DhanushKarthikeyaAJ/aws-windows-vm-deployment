# aws-windows-vm-deployment
Deploying a Windows Virtual Machine on AWS

# Deploying a Windows Virtual Machine on AWS

## Introduction

This guide provides step-by-step instructions for deploying a Windows virtual machine (VM) on AWS. By following these steps, you will be able to set up, configure, and connect to your Windows instance using the AWS Free Tier.

## Steps to Deploy

### 1. Sign In or Sign Up

- Log in to your [AWS Free Tier](https://aws.amazon.com/free/) account.
- If you do not have an account, create one by following the [sign-up instructions](https://aws.amazon.com/premiumsupport/knowledge-center/create-and-activate-aws-account/).

### 2. Launch an Instance

- Go to the EC2 dashboard.
- Click on **Launch Instance**.

### 3. Instance Name/Tag

- Provide a name or tag for your instance. Example: `windows-server`.

### 4. Choose an AMI

- Select a Windows AMI from the list. For example: “Microsoft Windows Server 2022 Base” (Free Tier eligible).

### 5. Select Instance Type

- Choose the instance type `t2.micro`, which is included in the Free Tier.

### 6. Key Pair Configuration

- If you already have a key pair, select it.
- If not, create a new key pair:
  - Click **Create New Key Pair**.
  - Enter a name, such as `awskey`.
  - Choose `RSA` as the key pair type and `.pem` as the file format.
  - Click **Create** to download the key pair.

### 7. Default VPC

- Use the default VPC settings for your instance.

### 8. Configure Security Groups

- Select an existing security group or use the default one.
- To add an RDP rule:
  - Go to **Security Groups**.
  - Select the default security group.
  - Click on **Inbound Rules** and then **Edit Inbound Rules**.
  - Add a new rule with:
    - **Type**: RDP
    - **Source**: Anywhere IPv4
  - Save the changes.

### 9. Launch the Instance

- Click **Launch Instance** to start your Windows virtual machine.

### 10. Retrieve RDP Credentials

- Go back to the EC2 Instances dashboard.
- Select your `windows-server` instance.
- Click **Connect**.
- Download the Remote Desktop file, save it, and open it.

### 11. Get the Instance Password

- In the **RDP Client** section of the instance details, click **Get Password**.
- Open the `.pem` key file you downloaded (or the existing one) with a text editor.
- Copy the contents of the key file and paste it into the **Private Key** field on the AWS console, then click **Decrypt Password**.
- Copy the generated password.

### 12. Connect via RDP

- Open the downloaded RDP file.
- Enter the decrypted password when prompted.
- Click **OK** and then **Yes** to connect.

### 13. Successful Connection

- You should now be connected to your Windows virtual machine.

## Troubleshooting

- **Connection Issues**: Ensure that the security group has the RDP rule configured correctly.
- **Password Issues**: Verify that you are using the correct `.pem` file and that it is properly decrypted.

For additional assistance, refer to the [AWS documentation](https://docs.aws.amazon.com/) or contact AWS support.

