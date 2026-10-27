# AWS EC2 Infrastructure with Terraform

Este repositório contém a declaração de infraestrutura como código (IaC) para o provisionamento e gerenciamento das instâncias EC2 na AWS usando **Terraform**.

---

## 🏛️ Arquitetura das Instâncias

Abaixo estão os detalhes das máquinas configuradas nesta infraestrutura:

| Parâmetro | Servidor 1 (App) | Servidor 2 (DB) |
| :--- | :--- | :--- |
| **Nome (Tag)** | `Cobaia1` | `Cobaia2` |
| **Instance Type** | `t3.micro`  | `t3.micro`  |
| **Base AMI ID** | `ami-0064a1e5f976e938b` | `ami-0884c330d44106119` |
| **Região AWS** | `sa-east-1` | `sa-east-1` |
---

## ⚙️ Pré-requisitos

Antes de executar o projeto, garanta que você possui os seguintes softwares instalados e configurados no seu ambiente:

1. **[Terraform CLI](https://developer.hashicorp.com/terraform/downloads)** (versão `>= 1.0.0`)
2. **[AWS CLI](https://aws.amazon.com/cli/)** instalada e autenticada
3. Credenciais da AWS configuradas localmente (`AWS_ACCESS_KEY_ID` e `AWS_SECRET_ACCESS_KEY`)

Para autenticar a AWS CLI no seu terminal, execute:
```bash
aws configure
```

---

## 🚀 Como Executar o Projetos

Siga a sequência abaixo no terminal a partir da raiz do repositório:

### 1. Inicializar o ambiente do Terraform
Baixa os provedores necessários (como o provedor da AWS):
```bash
terraform init
```

### 2. Validar a sintaxe dos arquivos
Garante que a sintaxe do `.tf` está correta:
```bash
terraform validate
```

### 3. Planejar as alterações (Dry-run)
Exibe o plano de execução para verificar quais recursos serão criados, alterados ou destruídos sem aplicar nada na conta:
```bash
terraform plan
```

### 4. Aplicar e provisionar a infraestrutura
Cria as instâncias na AWS conforme declarado:
```bash
terraform apply
```
> Confirme a execução digitando `yes` quando solicitado.

### 5. Destruir os recursos (Opcional)
Para encerrar e remover todos os recursos criados pelo Terraform na sua conta AWS:
```bash
terraform destroy
```

---

## 📁 Estrutura do Repositório

```text
.
├── .gitignore         # Ignora tfstate, arquivos temporários e chaves
├── .terraform.lock.hcl# Trava de versão dos providers
├── main.tf            # Declaração dos recursos AWS (EC2)
└── README.md          # Documentação do repositório
```