# Requirements

#### [prev](./concepts.md) | [home](./welcome.md)  | [next](./deployment-f19.md)

The WVD Docs article lists all requirements on the 'Overview' page located [here](https://docs.microsoft.com/en-us/azure/virtual-desktop/overview). 

> Note the documentation is split into [Spring 2020](https://docs.microsoft.com/en-us/azure/virtual-desktop/) release and [Fall 2019](https://docs.microsoft.com/en-us/azure/virtual-desktop/virtual-desktop-fall-2019/tenant-setup-azure-active-directory) release.

## Security
- An important point.

## Supporting infrastructure
- Azure subscription.
- Azure AD tenant.
- Domain Services: 
Host pool VMs must be domain joined to either an on-premises domain or to Azure AD Domain Services (AADDS).
- Users synced to Azure AD: this means deploying Azure AD Connect if using on-premises domain services.
- File Services: To enable persistent profile for users a file service is needed which supports domain integration. Azure Files can be used for this.
- Azure networking.
- Network connectivity to production systems.

## End to end connectivity
- Routing.
- Firewall rules.

## Access
- Global Administrator role.
- Subscription Contributor role.

## 'Split' or 'Single' deployment options

Decide to deploy all components to a single Azure AD Tenant or to split the WVD integration with a separate (non-production) Azure AD Tenant.

Split deployment: The majority of resources can be deployed to a Corp Azure AD Tenant. Specifc directory integration resources will be split and deployed separately. The cost of the split resources will be minimal, and a trial subscription can be used. 

Single deployment: this option requires that you manually setup your Azure AD and on-premises Domain Services integration. 

> At least one subscription per tenant is required with tenant trust enable. 
