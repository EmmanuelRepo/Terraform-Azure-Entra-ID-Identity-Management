# Terraform Azure Entra ID Automation  

🚀 **Automate Azure Entra ID User and Group Management with Terraform**  

This repository contains Terraform code to automate user and group management in **Azure Entra ID** (formerly Azure Active Directory). Transform manual processes into a scalable, consistent, and efficient **Infrastructure as Code (IaC)** solution.  

---

## 📋 **Features**  

- **Bulk User Creation from CSV**: Automatically create multiple users by reading data from a CSV file.  
- **Automated Group Management**: Dynamically create and manage Azure Entra ID groups.  
- **User-Group Association**: Associate users with the appropriate groups based on predefined rules.  
- **Service Principal Authentication**: Securely authenticate Terraform with Azure using a service principal.  
- **Scalable and Reusable Code**: Modular Terraform code designed for scalability and reusability.  

---

## 🚀 **Getting Started**  

### Prerequisites  

Before you begin, ensure you have the following:  

1. **Azure Subscription**: An active Azure subscription to create and manage resources.  
2. **Terraform Installed**: Install Terraform CLI on your local machine. Download it from [here](https://www.terraform.io/downloads.html).  
3. **Azure CLI**: Install Azure CLI and authenticate with your Azure account. Follow the instructions [here](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli).  
4. **Basic Understanding of Azure Entra ID**: Familiarity with Azure Entra ID concepts like users, groups, and service principals.  
5. **VS Code or Any Text Editor**: For writing and editing Terraform configuration files.  

---

### 🛠️ **Setup and Configuration**  

1. **Clone the Repository**:  
   ```bash
   git clone https://github.com/piyushsachdeva/Terraform-Azure-EntraID-Automation.git
   cd Terraform-Azure-EntraID-Automation
   ```

2. **Authenticate Terraform with Azure**:  
   - Create a Service Principal for Terraform:  
     ```bash
     az ad sp create-for-rbac --name "terraform-entra-id-automation" --role="Contributor" --scopes="/subscriptions/<SUBSCRIPTION_ID>"
     ```  
   - Set the following environment variables with the Service Principal credentials:  
     ```bash
     export ARM_CLIENT_ID="<CLIENT_ID>"
     export ARM_CLIENT_SECRET="<CLIENT_SECRET>"
     export ARM_SUBSCRIPTION_ID="<SUBSCRIPTION_ID>"
     export ARM_TENANT_ID="<TENANT_ID>"
     ```

3. **Prepare the CSV File**:  
   - Update the `users.csv` file with the user details (e.g., name, email, department).  
   - Example:  
     ```csv
     name,email,department
     John Doe,john.doe@example.com,IT
     Jane Smith,jane.smith@example.com,HR
     ```

4. **Initialize Terraform**:  
   ```bash
   terraform init
   ```

5. **Plan and Apply**:  
   - Review the execution plan:  
     ```bash
     terraform plan
     ```  
   - Apply the configuration to create users and groups:  
     ```bash
     terraform apply
     ```

---

## 📂 **Repository Structure**  

```plaintext
Terraform-Azure-EntraID-Automation/  
├── main.tf              # Main Terraform configuration for users and groups  
├── variables.tf         # Input variables for the Terraform configuration  
├── outputs.tf           # Outputs for the created resources  
├── users.csv            # Sample CSV file for bulk user creation  
├── README.md            # This README file  
└── .gitignore           # Specifies files to ignore in version control  
```

---

## 🤝 **Contributing**  

Contributions are welcome! If you have ideas for improvements or find any issues, please:  
1. Fork the repository.  
2. Create a new branch (`git checkout -b feature/YourFeatureName`).  
3. Commit your changes (`git commit -m 'Add some feature'`).  
4. Push to the branch (`git push origin feature/YourFeatureName`).  
5. Open a pull request.  

---

## 📜 **License**  

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.  

---

## 🙏 **Acknowledgments**  

- Special thanks to the Terraform and Azure communities for their incredible resources and support.  
- Inspired by the need for scalable and efficient identity management solutions.  

---

## 📧 **Contact**  

Have questions or feedback? Feel free to reach out:  
- **Email**: [Your Email]  
- **LinkedIn**: [Your LinkedIn Profile]  
- **GitHub**: [Your GitHub Profile]  

---

⭐ **If you find this project helpful, don't forget to give it a star!** ⭐  

Happy automating! 🚀
