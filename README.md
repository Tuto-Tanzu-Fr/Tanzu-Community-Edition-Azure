# Tuto Installation Tanzu CE sur Azure via Docker Desktop et UI

## Difficulté 2/5

## Connaissances nécessaires :
* ## Microsoft Azure niveau AZ900 : https://docs.microsoft.com/fr-fr/learn/certifications/exams/az-900
* ## Configuration Poste de travail Windows 10

# Section 1 Préparation Poste de Travail

* ## Docker desktop : https://docs.docker.com/desktop/windows/install/

* ## Kubectl sur W10 : https://kubernetes.io/docs/tasks/tools/install-kubectl-windows/

* ## W10 terminal : https://docs.microsoft.com/fr-fr/windows/terminal/install

* ## Compte Azure : https://azure.microsoft.com/fr-fr/free/

* ## Télécharger et installer Tanzu CE sur son poste: https://tanzucommunityedition.io/docs/latest/cli-installation/
    * ### Décompresser le ZIP 
    * ### Ouvrez un powershell en administrateur et lancer le script install
     * ### Le script va vous installer la CLI Tanzu
     * ### Modifier la variable PATH système pour que la CLI Tanzu soit prise en compte

    <br>

     ![Screenshot](./screenshots_tutos/install_tanzu_prerequis_1.JPG)

    <br>

     ![Screenshot](./screenshots_tutos/install_tanzu_prerequis_2.JPG)


<br>

# Section 2 Préparation sur Azure

## Conseil : Sur le portail Azure utilisez au maximum la barre de recherche pour trouver les ressources. Exemples : Resource Group / APP Registration / Subscriptions

## Créer son RG 

<br>

![Screenshot](./screenshots_tutos/install_tanzu_azure_4.JPG)

<br>

## Créer son APP Regsitration Tanzu et sauvegarder son secret

<br>

![Screenshot](./screenshots_tutos/install_tanzu_azure_3.JPG)

<br>

## Créer son secret pour son APP Registration
* # Attention sauvegarder votre secret car Azure ne l'affiche qu'une fois

<br>

![Screenshot](./screenshots_tutos/install_tanzu_azure_7.JPG)

<br>

## Donner le rôle OWNER ou CONTRIBUTOR a son APP Registration sur sa subscription
* # Donner le rôle OWNER ou CONTRIBUTOR a votre APP Registration

<br>

![Screenshot](./screenshots_tutos/install_tanzu_azure_8.JPG)

<br>

![Screenshot](./screenshots_tutos/install_tanzu_azure_9.JPG)

<br>

## Créer une clé SSH

<br>

![Screenshot](./screenshots_tutos/install_tanzu_azure_6.JPG)

<br>

## Commande pour accepter le contrat d'utilisation sur le marketplace Azure : 

<br>

```
Get-AzureRmMarketplaceTerms -Publisher "vmware-inc" -Product "tkg-capi" -Name "k8s-1dot21dot2-ubuntu-2004" | Set-AzureRmMarketplaceTerms -Accept
```

<br>

# Si besoin voici la documentation VMWARE : https://docs.vmware.com/en/VMware-Tanzu-Kubernetes-Grid/1.2/vmware-tanzu-kubernetes-grid-12/GUID-mgmt-clusters-azure.html

<br>

# Section 3 Installation automatisé via UI

<br>

```
tanzu management-cluster create --ui
```

<br>

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

<br>

# Section 4 Connection au cluster Tanzu CE

## Attention avant de vous lancez vos commandes, vérifier que docker desktop est démarrer avec le cluster 

<br>

```
tanzu management-cluster get
```

<br>

## Résultat attendu :

<br>

![Screenshot](./screenshots_tutos/install_tanzu_connection_1.JPG)

<br>

```
tanzu management-cluster kubeconfig get --admin
```

<br>

## Résultat attendu :

<br>

![Screenshot](./screenshots_tutos/install_tanzu_connection_2.JPG)

<br>

```
kubectl config use-context tanzu-mgtcluster-admin@tanzu-mgtcluster
```

<br>

## Résultat attendu :

<br>

![Screenshot](./screenshots_tutos/install_tanzu_connection_3.JPG)

<br>

```
kubectl get nodes
```
<br>

## Résultat attendu :

<br>

![Screenshot](./screenshots_tutos/install_tanzu_connection_4.JPG)

<br>
