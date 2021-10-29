## Bienvenue sur mon Tuto Tanzu avec Azure

## Section 1 Pré-requis

* ## Docker desktop : https://docs.docker.com/desktop/windows/install/

* ## Kubectl sur windows : https://kubernetes.io/docs/tasks/tools/install-kubectl-windows/

* ## Windows terminal : https://docs.microsoft.com/fr-fr/windows/terminal/install

* ## Compte Azure : https://azure.microsoft.com/fr-fr/free/

* ## Télécharger et Installer Tanzu Community Edition sur son poste: https://tanzucommunityedition.io/docs/latest/cli-installation/
    * ### Tanzu CLI

<br>

### Section 2 Configuration Azure

* ## Créer son APP Regsitration Tanzu et sauvegarder son secret

* ## Donner le bon rôle a son APP Registration sur sa subscription

* ## Doc officiel vmware : https://docs.vmware.com/en/VMware-Tanzu-Kubernetes-Grid/1.2/vmware-tanzu-kubernetes-grid-12/GUID-mgmt-clusters-azure.html

* ## Commande pour accepter le contrat d'utilisation sur le marketplace Azure : 

```
Get-AzureRmMarketplaceTerms -Publisher "vmware-inc" -Product "tkg-capi" -Name "k8s-1dot21dot2-ubuntu-2004" | Set-AzureRmMarketplaceTerms -Accept
```

<br>

## Section 3 Installation automatisé via l'interface web

```
tanzu management-cluster create --ui
```

![Screenshot](./screenshots_tutos/install_tanzu_azure_1.JPG)

<br>

![Screenshot](./screenshots_tutos/install_tanzu_azure_2.JPG)

<br>

