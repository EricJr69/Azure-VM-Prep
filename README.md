# Configuring and Implementing a Honeypot in Azure



![Banner](https://github.com/AmiliaSalva/Azure-VM-Prep/assets/132176058/5ea56352-1c7f-4f4a-a243-272f6fbd9ee5)

### Let's start setting up our Azure Honeynet project. First, we must create virtual machines (VMs) in Microsoft Azure. These cloud-based computers will form the core of our honeynet. Here's how we'll get started:

1. **Sign in to the Azure portal:** The first step is to log into your Azure account. If you don't have an account yet, **[you'll need to create one!](https://portal.azure.com)**

<details close> 
<summary> 2. Create a virtual machine: </summary>




- Once you're in the Azure portal, navigate to the 'Virtual machines' section. 
  
  ![azure portal](https://github.com/AmiliaSalva/Azure-VM-Prep/assets/132176058/89174131-d43a-444b-b3f9-e4b7972d0041)

  
  
- Click on 'Create,' then 'Virtual machine.' This is where we'll set up our new VM!
  
 
  ![VM create](https://github.com/AmiliaSalva/Azure-VM-Prep/assets/132176058/f8cc721b-2439-4390-9552-06a51b996918)
  
  </details>
  
  
  <details close> 
<summary> 3. Configure the VM settings: </summary>
  
  - **Subscription and resource group:** Select your Azure subscription and resource group. For this project, use the existing resource group ```RG-Cyber-Lab2``` 
  
  - **Virtual Machine Name:** Name your VM ```Lab-HoneyNet```

  - **Region:**  Choose the region, ```(US) East US 2```
  
  - **Availability Options:** Select ```No infrastructure redundancy required``` since this VM will act as a honeypot.

  - **Image:** Select ```Windows 10 Pro, version 21H2 - x64 Gen2```
  
  ![VM create](https://github.com/AmiliaSalva/Azure-VM-Prep/assets/132176058/10525f40-6634-4cef-b519-0487d492c878)
  
  - **Networking**: Use the default settings for the virtual network. For this lab, name it ```Lab-VNet```.
  
  ![netowkr](https://github.com/AmiliaSalva/Azure-VM-Prep/assets/132176058/8fe63ac8-42a9-4bea-bab0-2575013c185c)


  </details>


<details close> 
<summary> 4. NSG/Inbound Security Rule Configuration: </summary>
 
  - **Navigate to the Network Security Group (NSG):** In the Azure portal, search for 'Network Security Groups' in the search bar and select the NSG associated with your virtual machine.
  
  - **Create an inbound security rule:** Inside the NSG, you'll find a section for 'Inbound security rules'. This is where we control what kind of traffic is allowed to reach our VM. Click on 'Add' to create a new rule.

  - **Configure the rule:** We will be prompted to input details about the new rule. Configure the following settings:
  
  - **Source:** Set to ```Any``` to allow traffic from any location.
  
  - **Source port ranges:** Set to ```*``` or ```Any``` to allow all ports.

  - **Destination:** Set to ```Any```to direct traffic to your VM.
  
  - **Destination port ranges:** Set to ```*``` or ```Any``` to open all ports.
  
  - **Priority:** Set the priority to ```300``` for this lab. Note that lower-priority numbers are processed before higher-priority numbers.

  - **Action:** Set to ```Allow``` to permit traffic matching this rule.
 
  
 ![NSG](https://github.com/AmiliaSalva/Azure-VM-Prep/assets/132176058/feb1442a-8ee7-4c78-bb98-018858b85f99)

  
  - **Review & Create:** - After configuring the rule details, click 'Add' to create the new inbound security rule.
 
 
 
 
 
 
 
 
 
</details>

# Conclusion

### By creating our Virtual Machines (VMs) and opening inbound security rules, we intentionally make our system vulnerable to attacks. This is not recommended for production environments, as it poses significant security risks.

### However, in the context of our honeynet project, this setup serves a specific purpose. We're creating a decoy environment that attracts potential attackers by leaving our VM exposed.

### This allows us to monitor and analyze their actions in a controlled environment.
 
