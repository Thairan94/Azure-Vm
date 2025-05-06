# Azure-Vm
Este repositório contém **resumos, anotações e dicas rápidas** sobre o uso da plataforma **Microsoft Azure**, com foco no aprendizado prático e direto ao ponto

## 📌 O que é Azure?

- Plataforma de **serviços em nuvem da Microsoft**.
- Oferece soluções de **computação, armazenamento, rede, banco de dados, IA** e muito mais.
- Permite **escalar aplicações**, criar VMs, hospedar APIs, configurar redes virtuais, entre outros.

# ☁️ Benefícios do Microsoft Azure
---

## 🔹 Alta Disponibilidade

- Infraestrutura global com **datacenters distribuídos** em várias regiões.
- Garantia de **tempo de atividade (SLA)** de até 99,99% para muitos serviços.
- Redundância e failover automático para manter sistemas ativos mesmo diante de falhas.

---

## 🔹 Escalabilidade e Elasticidade

- Permite **aumentar ou reduzir recursos sob demanda**, de forma automática ou manual.
- Ideal para aplicações com variação de carga, como e-commerces ou apps sazonais.
- Escalabilidade **horizontal (adicionar instâncias)** ou **vertical (aumentar poder de uma instância)**.

---

## 🔹 Confiabilidade

- Dados replicados em **múltiplas zonas de disponibilidade**.
- Backup automático, recuperação de desastres e serviços resilientes.
- Monitoramento contínuo com alertas e logs detalhados.

---

## 🔹 Previsibilidade

- Modelos de precificação **baseados em consumo** (pay-as-you-go).
- Facilidade para **prever custos** com ferramentas como **Azure Pricing Calculator**.
- Oferece alertas e limites de orçamento para evitar surpresas na cobrança.

---

## 🔹 Segurança

- Infraestrutura protegida por **criptografia em trânsito e em repouso**.
- Suporte a **firewalls, VPNs, redes privadas virtuais (VNets)** e **NSGs**.
- Conformidade com padrões como **ISO, GDPR, SOC, HIPAA**.

---

## 🔹 Governança

- Permite aplicar **políticas de acesso e uso** com Azure Policy e Azure Blueprints.
- **Controle granular de permissões** com RBAC (Controle de Acesso Baseado em Função).
- Gerenciamento centralizado de recursos por grupos, assinaturas e tags.

---

## 🔹 Gerenciabilidade

- Interface intuitiva via **portal web, CLI, PowerShell e APIs**.
- Integração com **monitoramento, logs e dashboards personalizados**.
- Serviços como **Azure Monitor, Log Analytics e Application Insights** ajudam no diagnóstico e operação.

---

> 🔧 O Microsoft Azure entrega uma nuvem completa, segura e flexível — ideal para empresas de todos os tamanhos modernizarem suas aplicações e operações.

# 💻 Criando e Configurando uma Máquina Virtual no Microsoft Azure

Este guia apresenta o passo a passo para criar uma **máquina virtual Windows** no **portal Azure**, conectar-se a ela via RDP e instalar um servidor Web IIS.

---

## 🌐 Acesso ao Portal

1. Acesse: [portal Azure - VM Windows (tutorial oficial)](https://learn.microsoft.com/pt-br/azure/virtual-machines/windows/quick-create-portal)
2. No campo de pesquisa, digite **"Máquinas virtuais"** e clique no serviço correspondente.
3. Clique em **Criar > Máquina virtual do Azure**.

---

## ⚙️ Configuração da VM

### 🔸 Detalhes da Instância
- **Nome da VM:** `myVM`
- **Imagem:** `Windows Server 2022 Datacenter: Azure Edition - x64 Gen 2`
- **Região, tamanho e outros:** deixar como padrão

> ℹ️ Alguns usuários verão a opção de escolher **zonas de disponibilidade** — útil para alta disponibilidade.

### 🔸 Conta de Administrador
- Nome de usuário: `azureuser`
- Senha: mínimo de 12 caracteres com complexidade

### 🔸 Regras de Porta de Entrada
- Selecione: `Permitir portas selecionadas`
- Escolha: `RDP (3389)` e `HTTP (80)`

Clique em **Examinar + Criar**, depois em **Criar**.

---

## 📥 Conectando à Máquina Virtual

1. Após a implantação, clique em **Ir para o recurso**.
2. Clique em **Conectar > RDP**.
3. Clique em **Baixar arquivo RDP** e abra-o.
4. Selecione **Mais opções > Usar uma conta diferente**.
   - Usuário: `localhost\azureuser`
   - Senha: (a que você criou)
5. Ignore o aviso de certificado, clique em **Sim**.

---

## 🌐 Instalando o Servidor Web IIS

Com a VM conectada via RDP:

1. Abra o **PowerShell** como Administrador.
2. Execute o seguinte comando:

```powershell
Install-WindowsFeature -name Web-Server -IncludeManagementTools
Aguarde a instalação e depois feche a conexão.
