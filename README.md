# Publish a single container to Azure

## Pré-requisitos

* [Azure CLI](https://docs.microsoft.com/en-us/cli/azure/?view=azure-cli-latest)

## Passo a passo

* Realizar login na sua conta Azure ```az login```

* Criar um resource group:

   ```bash
   az group create -l westeurope -n deployaks
   ```

* Criar o cluster
  
  ```bash
  az aks create -g deployaks -n clusterw2q2 --node-count 1 --generate-ssh-keys
  ```

* Instalar o kubctl

  ```bash
  az aks install-cli
  ```

* Recupera credenciais e nodos

  ```bash
  az aks get-credentials -g deployaks -n clusterw2q2
  kubectl get nodes
  ```

* Acessar o endereço (neste caso):

  ```bash
  40.118.127.81
  ```