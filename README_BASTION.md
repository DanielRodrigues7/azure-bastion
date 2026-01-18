# Azure Bastion – Acesso Seguro a Máquinas Virtuais no Azure

Este repositório demonstra como utilizar o **Azure Bastion** para acessar máquinas virtuais Linux e Windows de forma segura, **sem expor IPs públicos** e sem abrir portas como 22 (SSH) e 3389 (RDP).

Toda a documentação aqui é baseada em um laboratório real, acompanhado por prints e passos organizados.

---

## 🔎 O que é o Azure Bastion?

O **Azure Bastion** é um serviço PaaS que permite acessar VMs diretamente pelo navegador usando **RDP** ou **SSH**, sem necessidade de:
- IP público nas VMs
- Jump servers
- Regras de firewall abertas para a internet

Com isso, o ambiente fica mais seguro e segue boas práticas de Zero Trust.

---

## 🏗 Arquitetura do Laboratório

O laboratório possui:

- 1 Bastion Host: `bastion-01`
- 1 VM Linux sem IP público: `vm-linux01`
- 1 VM Windows sem IP público: `vm-win01`
- 1 VNet com subnet dedicada `AzureBastionSubnet`

### 📸 VMs sem IP público
![vm sem IP publicos](citeturn17image22)

---

## ⚙️ 1. Criando e configurando o Azure Bastion

Após criar o recurso, é possível visualizar os detalhes do Bastion:

### 📸 Tela de visão geral do Bastion
![bastion](citeturn17image21)

O Bastion precisa obrigatoriamente da subnet:

```
AzureBastionSubnet
```
Com máscara mínima **/26**.

---

## 🔗 2. Usando Links Compartilháveis do Bastion

Com os links compartilháveis, você permite que um usuário acesse a VM via Bastion **sem acessar o Portal do Azure**.

### 📸 Links compartilháveis configurados
![link compartilhado](citeturn17image18)

### 📸 Tela do usuário acessando via link compartilhável
![link](citeturn17image17)

---

## 🖥️ 3. Acesso a máquina Windows via Bastion (RDP)

### 📸 Conexão Bastion → VM Windows
![win-conexao](citeturn17image20)

Após autenticar:

### 📸 Windows acessado via Bastion pelo navegador
![win-server](citeturn17image19)

---

## 🐧 4. Acesso a máquina Linux via Bastion (SSH)

### 📸 Tela de conexão SSH pelo Bastion
![conexao](citeturn17image19)

Você pode autenticar usando:
- Senha
- Chave pública

A sessão abre diretamente no navegador.

---

## 🛡️ 5. Benefícios do Azure Bastion

- Nenhum IP público necessário
- Elimina abertura das portas 22/3389
- Navegador como cliente RDP/SSH
- Acesso totalmente privado dentro da VNet
- Zero configuração de firewall exposto
- Aumenta segurança e reduz superfície de ataque

---

## 🎯 Conclusão

O Azure Bastion é uma solução robusta e segura para acessar máquinas virtuais no Azure sem comprometer a segurança da rede.

Este projeto tem o objetivo de documentar o laboratório, demonstrando na prática como:
- Criar o Bastion
- Proteger VMs sem IP público
- Conectar via RDP e SSH
- Utilizar links compartilháveis

É um excelente exercício para quem está estudando **Azure**, **Infraestrutura em Nuvem** e **boas práticas de segurança**.

---

## 📁 Estrutura do Repositório

```
README.md
imagens/
    bastion.png
    link.png
    link_compartilhado.png
    conexao.png
    win-conexao.png
    vm_sem_ip_publicos.png
```

---

## 📫 Contato
- LinkedIn: https://www.linkedin.com/in/daniel-rodrigues-358b41121/
- Email: daniel07.rodrigues@hotmail.com
