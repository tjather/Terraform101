# Terraform101

## Overview
This project utilizes **Terraform** to provision and manage **Virtual Machines (VMs) on Microsoft Azure** to create basic instances.

## Features
- **Automated VM Provisioning**: Define and deploy Azure VMs using Terraform.
- **State Management**: Track deployed resources using Terraform state files.
- **Flexible Configuration**: Customize VM settings via variables.
- **Scalability**: Modify infrastructure easily without manual intervention.

## Prerequisites
To run this project, you need the following:
- **Terraform** (Download from [Terraform.io](https://www.terraform.io/downloads))
- **Azure Subscription** with access credentials
- **Azure CLI** (Install via `brew install azure-cli` or [Microsoft Docs](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli))
- **An SSH Key Pair** for secure access to VMs

## Project Structure
```
├── main.tf          # Defines the Azure VMs and networking configuration
├── variables.tf     # Stores customizable parameters (e.g., VM size, region, etc.)
├── output.tf        # Specifies outputs such as VM IP addresses
├── terraform.tfstate  
├── terraform.tfstate.backup 
└── README.md      
```

## Setup & Deployment
### Step 1: Authenticate with Azure
Before running Terraform, log in to Azure:
```sh
az login
```

### Step 2: Initialize Terraform
Run the following command to download necessary providers and initialize Terraform:
```sh
terraform init
```

### Step 3: Plan the Deployment
Check what changes Terraform will apply without making any actual modifications:
```sh
terraform plan
```

### Step 4: Apply the Configuration
Deploy the VMs and associated resources:
```sh
terraform apply
```
Confirm the action when prompted.

### Step 5: Retrieve Output Information
After deployment, get the VM IP addresses and other output values:
```sh
terraform output
```

### Step 6: Destroy Resources (Optional)
To remove all infrastructure created by Terraform, use:
```sh
terraform destroy
```

## Customization
Modify `variables.tf` to customize VM specifications, such as:
```hcl
variable "vm_size" {
  default = "Standard_B1s"
}
```
