# Deploy a Virtual Machine via Custom Templates

**Course:** 26F_CST8911_300 Introduction to Cloud Computing  
**Student:** Samuel Vachon
**Student Number:** 041101891

I deployed a Linux VM in East US using the Azure portal's **Deploy a custom template** service. The [ARM template](template.json) defines the VM, network interface, and virtual network. I provided the administrator password at deployment using the secure password parameter.

## Deployed configuration

| Setting                            | Value                                 |
| ---------------------------------- | ------------------------------------- |
| Resource group                     | `CST8911-CustomTemplate-Lab`          |
| Virtual machine                    | `cst8911-template-vm`                 |
| Region                             | East US                               |
| Availability                       | No infrastructure redundancy required |
| Security type                      | Standard                              |
| Image                              | Canonical Ubuntu Pro 22.04 LTS        |
| Size                               | `Standard_B2as_v2`                    |
| Authentication                     | Password, username `azureuser`        |
| OS disk                            | Standard SSD LRS, 30 GiB              |
| Virtual network / subnet           | `cst8911-lab-vnet` / `snet-eastus-1`  |
| Public IP and public inbound ports | None                                  |
| NIC network security group         | None                                  |
| Load balancing                     | None                                  |
| VM tag                             | `Purpose = CustomTemplateLab`         |

The required `Standard_B1ls` size was unavailable in East US under my CloudLabs subscription, so I used `Standard_B2as_v2`. The deployed image was the Pro edition of Ubuntu 22.04 LTS.

## Verification and cleanup

The [custom deployment review](screenshots/03-custom-template-deployment-succeeded.png) shows the inputs used. The running VM and tag screenshots below show the deployed result.

- [VM setup review](screenshots/01-vm-review-basics.png)
- [Running VM overview](screenshots/04-vm-overview.png)
- [OS disk](screenshots/05-vm-os-disk.png)
- [Deployed network settings](screenshots/06-vm-networking.png)
- [Load balancing](screenshots/07-vm-load-balancing.png)
- [VM tag after redeployment](screenshots/08-vm-tag.png)
- [Resource group deletion verification](screenshots/09-resource-group-deleted.png)
