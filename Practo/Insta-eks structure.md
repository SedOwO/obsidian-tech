1 Terraform bastion(region specific)
India bastion is connected to this bastion, UAE is not(?)
Kuber Servers are connected to the Terraform bastion

#### Add new users
- setup TOTP
- create the user

#### Login into the Terraform machine(tf-codebase)
```bash
# rolebased ssh
tssh ubuntu prod-eks-tf
```

tf commands work only in the tf directory

#### Upgrade EKS

1. `tf validate`: validates for any syntax errors
2. `tf plan`: shows what all changes will be made
3. `tf apply`: the update is applied and takes about 20-30 mins to upgrade

> Note: **Gravitons** are the cheapest and newly avaliable eks machines(around 30% cheaper than intel or amd)

> Note: **argocd** to debug

> Note: for any changes to be applied, the code SHOULD be pushed to github(`master` or `develop` branch.)

#### Argocd
To access argocd dashboard, you will have to setup **2 tunnels** one from **local machine** another from the **ELB**.