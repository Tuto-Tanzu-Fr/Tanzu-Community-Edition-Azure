## Bienvenue sur mon Tuto Tanzu avec Azure

## Section 1 Préparation Poste de Travail

* ## Docker desktop : https://docs.docker.com/desktop/windows/install/

* ## Kubectl sur windows : https://kubernetes.io/docs/tasks/tools/install-kubectl-windows/

* ## Windows terminal : https://docs.microsoft.com/fr-fr/windows/terminal/install

* ## Compte Azure : https://azure.microsoft.com/fr-fr/free/

* ## Télécharger et Installer Tanzu Community Edition sur son poste: https://tanzucommunityedition.io/docs/latest/cli-installation/
    * ### Vous décompresser le ZIP
    * ### Ouvrez un powershell en administrateur et lancer le script install
     * ### Le script va vous installer la CLI Tanzu
     * ### Modifier la variable PATH système pour que la CLI Tanzu soit prise en compte

     ![Screenshot](./screenshots_tutos/install_tanzu_prerequis_1.JPG)
    <br>
     ![Screenshot](./screenshots_tutos/install_tanzu_prerequis_2.JPG)


<br>

### Section 2 Préparation sur Azure

* ## Créer son RG 

![Screenshot](./screenshots_tutos/install_tanzu_azure_4.JPG)

* ## APP Regsitration Tanzu et sauvegarder son secret

![Screenshot](./screenshots_tutos/install_tanzu_azure_3.JPG)

<br>

* ## Créer son secret pour son APP Registration
    * # Attention sauvegarder votre secret car Azure ne l'affiche qu'une fois

![Screenshot](./screenshots_tutos/install_tanzu_azure_7.JPG)

* ## Donner le bon rôle a son APP Registration sur sa subscription
    * # Donner le rôle Owner a votre APP Registration

![Screenshot](./screenshots_tutos/install_tanzu_azure_8.JPG)

<br>

![Screenshot](./screenshots_tutos/install_tanzu_azure_9.JPG)

* ## Créer une clé SSH

![Screenshot](./screenshots_tutos/install_tanzu_azure_6.JPG)

* ## Commande pour accepter le contrat d'utilisation sur le marketplace Azure : 

```
Get-AzureRmMarketplaceTerms -Publisher "vmware-inc" -Product "tkg-capi" -Name "k8s-1dot21dot2-ubuntu-2004" | Set-AzureRmMarketplaceTerms -Accept
```

<br>

Doc officiel vmware : https://docs.vmware.com/en/VMware-Tanzu-Kubernetes-Grid/1.2/vmware-tanzu-kubernetes-grid-12/GUID-mgmt-clusters-azure.html

## Section 3 Installation automatisé via l'interface web

```
tanzu management-cluster create --ui
```

![Screenshot](./screenshots_tutos/install_tanzu_azure_1.JPG)

<br>

![Screenshot](./screenshots_tutos/install_tanzu_azure_2.JPG)

<br>

![Screenshot](./screenshots_tutos/install_tanzu_azure_10.JPG)

<br>

![Screenshot](./screenshots_tutos/install_tanzu_azure_11.JPG)

<br>

![Screenshot](./screenshots_tutos/install_tanzu_azure_12.JPG)

<br>

![Screenshot](./screenshots_tutos/install_tanzu_azure_13.JPG)

<br>

![Screenshot](./screenshots_tutos/install_tanzu_azure_14.JPG)

<br>

![Screenshot](./screenshots_tutos/install_tanzu_azure_15.JPG)

<br>

![Screenshot](./screenshots_tutos/install_tanzu_azure_16.JPG)

<br>

![Screenshot](./screenshots_tutos/install_tanzu_azure_17.JPG)

<br>

![Screenshot](./screenshots_tutos/install_tanzu_azure_18.JPG)

## Section 4 Connection au cluster Tanzu CE

```
tanzu management-cluster get
```
<br>

```
tanzu management-cluster kubeconfig get --admin
```

<br>

```
kubectl config use-context tanzu-mgtcluster-admin@tanzu-mgtcluster
```

<br>

```
kubectl get nodes
```

tanzu package repository add tce-repo --url projects.registry.vmware.com/tce/main:0.9.1 --namespace tanzu-package-repo-global