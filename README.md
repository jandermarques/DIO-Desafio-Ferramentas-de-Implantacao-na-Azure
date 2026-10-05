# DIO Desafio - Ferramentas de Implantação na Azure

Este documento apresenta uma visão didática sobre ferramentas e conceitos fundamentais do **Microsoft Azure**, incluindo **Cloud Shell**, **Azure Arc**, **Azure Resource Manager (ARM)**, **Infraestrutura como Código**, **Modelos ARM** e **Bicep**.

---

## ☁️ Cloud Shell da Azure

O **Azure Cloud Shell** é um ambiente de linha de comando baseado em navegador, integrado ao portal do Azure, que permite gerenciar recursos sem necessidade de instalação local.

- **Overview**:  
  - Ambiente interativo acessível diretamente pelo portal.  
  - Executa scripts e comandos para administração de recursos.  
  - Já vem com ferramentas pré-instaladas (Azure CLI, PowerShell, Git, etc.).

- **Opções disponíveis**:  
  - **PowerShell**: ideal para administradores Windows e automação com cmdlets.  
  - **Bash**: voltado para usuários Linux e scripts shell.  

- **Barra de botões**:  
  - Upload/Download de arquivos.  
  - Alternar entre Bash e PowerShell.  
  - Gerenciar configurações de armazenamento persistente.  

- **Comando `help`**:  
  - Exibe lista de comandos disponíveis e instruções de uso.  
  - Exemplo: `az --help` mostra opções do Azure CLI.  

---

## 🌐 Azure Arc

O **Azure Arc** estende os serviços e políticas do Azure para ambientes **multicloud, locais e edge**.

- Permite registrar servidores físicos, VMs de outras nuvens e clusters Kubernetes no Azure.  
- Oferece **governança unificada**: aplicar **Azure Policy**, monitoramento e segurança em qualquer infraestrutura.  
- Simplifica a gestão híbrida, trazendo consistência entre ambientes diferentes.  

---

## 🛠️ Azure Resource Manager (ARM)

O **ARM** é a camada de gerenciamento do Azure que controla a criação, atualização e exclusão de recursos.

- **Funções principais**:  
  - Aplicar controle de acesso (RBAC).  
  - Gerenciar dependências entre recursos.  
  - Suporte a **tags** e **locks**.  
  - Base para automação via templates (JSON/Bicep).  

---

## 📐 Infraestrutura como Código (IaC)

A **Infraestrutura como Código** é o conceito de gerenciar e provisionar recursos de TI por meio de arquivos declarativos.

- **Benefícios**:  
  - Consistência entre ambientes.  
  - Versionamento em sistemas como Git.  
  - Automação e repetibilidade.  
- **Ferramentas no Azure**: ARM Templates (JSON), Bicep, Terraform.  

---

## 📄 Modelos do ARM (Azure Resource Manager)

- São arquivos em **JSON** que descrevem recursos do Azure.  
- Permitem **implantações repetíveis e consistentes**.  
- Estrutura baseada em pares chave-valor.  
- Exemplo de uso: criar uma VM com configuração pré-definida.  

---

## 🧩 Bicep

O **Bicep** é uma linguagem declarativa simplificada que compila para ARM Templates (JSON).

- **Características**:  
  - Sintaxe mais limpa e legível que JSON.  
  - Exclusiva para o Azure.  
  - Facilita modularização e reutilização de código.  

- **Exemplo simples em Bicep**:
  ```bicep
  resource myStorage 'Microsoft.Storage/storageAccounts@2021-04-01' = {
    name: 'mystorageaccount'
    location: 'eastus'
    sku: {
      name: 'Standard_LRS'
    }
    kind: 'StorageV2'
  }
