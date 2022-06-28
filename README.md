# AD-Connect

# What is the purpose of AD-Connect?
- AD Connect is used to sync the users accounts and credentials stored on an on-premises AD environment to the Azure AD environment.
- Some organizations will have an AD on prem and also have Azure AD users, in order to sync the two so that on-prem AD environment and Azure AD users can exchange resources.
- Azure AD Connect Component would need to be installed on a separate Windows Server which would be domain joined to the Active Directory domain. The Azure AD Connect Component would fetch the users from AD and sync it to Azure AD.




Two types of synchronization process in Azure AD
1. <em> Password Hash Synchornization </em> (AD duplicated to Azure AD) - Password of the user is also replicated to Azure AD.
- Azure AD Connect synchronizes a hash, of the hash, of a user's password from an on-premises Active Directory instance to a cloud-based Azure AD instance.
- Users can use the same username and password to log onto resources in the on premises environment and the Azure AD environment
2. <em> Alternative for cloud authetnication is Pass through authentication </em> is where users can log into both the on premises environment and the Azure AD environment BUT authentication happens at the on-prem AD first because not all feautures of AD is present in Azure AD. This allows organizations to enforce their on-premise Active Directory security and password policies.

- If a user changes a password in AD, it will automatically get sync to Azure AD with Password Hash Synchronization.

# What are the two components for the Azure AD Connect service?
- Azure AD Connect sync component - must be installed on the on-premise environment
- Azure AD Connect sync service - is ran in Azure AD

# How would IT Amins use Azure AD Connect? What are the pre-requisites?
- Ensure an Azure AD tenant is in place
- Add and verify the company's domain in Azure AD
- Use IdFix tool to identify errors such as duplicates and formatting problems in the on-premise directory
- The Azure AD Connect sync component must be installed on a Windows Server 2012 Standard or better. The server must have the full GUI installed. The server must be domain joined. Ideally this component must not be installed on the domain controller.
- The Azure AD Connect sync component requires a SQL Server database for storing identity data. By default , the installation of Azure AD Connect will install SQL Server 2012 Express LocalDB.

# During the configuration of the Azure AD Connect sync component, you need to use an

- Azure AD Global Administrator account for the Azure AD tenant. The account should be a school or organization account and cannot be a Microsoft account

- An Enterprise Administrator account for the on-premise Active Directory

- The Azure AD Connect server needs DNS resolution for both intranet and internet. The DNS server must be able to resolve names both to your on-premises Active Directory and the Azure AD endpoints


# What if we change a password in Azure AD, will it get synced to the local AD? 
- It will only get synced from Azure AD to an on-premises AD with <em> password writeback </em>


