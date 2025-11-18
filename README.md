📘 MyIacProject – Infraestrutura Completa com AWS CloudFormation

Este projeto demonstra a criação de uma infraestrutura completa na AWS utilizando Infrastructure as Code (IaC) via CloudFormation.
Foram criados dois templates principais:

infra.yaml → Infraestrutura base (VPC, sub-redes, rotas, NAT, Segurança)

app.yaml → Camada de aplicação (EC2 + S3 + Apache + IAM)

O objetivo foi construir um ambiente organizado, isolado e funcional, seguindo boas práticas de arquitetura em nuvem.

🚀 Arquitetura Geral

A infraestrutura final criada inclui:

VPC customizada (10.0.0.0/16)

Sub-rede pública

Sub-rede privada

Internet Gateway

NAT Gateway

Tabelas de rotas públicas e privadas

Security Group com regras mínimas

Bucket S3 para site estático

EC2 em subnet privada com Apache instalado via UserData

IAM Role + Instance Profile para acesso S3 e SSM

A instância EC2 é acessada via AWS Systems Manager (SSM), sem exposição de portas públicas — prática recomendada de segurança.

**🧩 1. Infraestrutura (infra.yaml)**

**▶️ 1.1. VPC Criada**
<img src="https://github.com/cauafreirealves/MyIacProject/blob/main/VPC_Criada.jpeg">

**▶️ 1.2. Sub-redes (Pública e Privada)**

<img src="https://github.com/cauafreirealves/MyIacProject/blob/main/SubRedes.jpeg">

**▶️ 1.3. Tabelas de Rotas (Pública e Privada)**

<img src="https://github.com/cauafreirealves/MyIacProject/blob/main/TabelaDeRotasjpeg.jpg">

**▶️ 1.4. NAT Gateway**
<img src="https://github.com/cauafreirealves/MyIacProject/blob/main/Natgateway.jpg">

**▶️ 1.5. Internet Gateway**
<img src="https://github.com/cauafreirealves/MyIacProject/blob/main/InternetGateway.jpg">

**▶️ 1.6. Security Group**
<img src="https://github.com/cauafreirealves/MyIacProject/blob/main/GruposDeSeguran%C3%A7a.jpg">

**▶️ 1.7. Stack Infraestrutura (Status Create Complete)**
<img src="https://github.com/cauafreirealves/MyIacProject/blob/main/stack_Infra.jpg">

**🖥️ 2. Aplicação (app.yaml)**

A camada de aplicação cria:

Bucket S3 (com website hosting)

IAM Role da EC2

Instance Profile

EC2 privada com:

Apache instalado automaticamente

Página HTML criada pelo UserData

Acesso ao S3

Acesso SSM (sem SSH)

**▶️ 2.1. Buckets Criados**
<img src="https://github.com/cauafreirealves/MyIacProject/blob/main/BucketsCriados.jpg">

**▶️ 2.2. Instância EC2 Criada (em Sub-rede Privada)**
<img src="https://github.com/cauafreirealves/MyIacProject/blob/main/InstanciaCriada.jpg">

**▶️ 2.3. Terminal da EC2 via SSM**
<img src="https://github.com/cauafreirealves/MyIacProject/blob/main/terminal.jpg">
Aqui validei:

Apache rodando

UserData funcionando

Conectividade via NAT

Retorno da página HTML


<!-- PRINT: Terminal EC2 / curl localhost -->
**▶️ 2.4. Stack App (Create Complete)**
<img src="https://github.com/cauafreirealves/MyIacProject/blob/main/Stack_App.jpg">
📄 3. Templates do Projeto

Os templates YAML utilizados estão neste repositório:

infra.yaml

app.yaml

Eles podem ser reutilizados e adaptados para diferentes cenários.

🔍 4. Fluxo de Funcionamento da Aplicação

EC2 privada inicia

UserData instala o Apache

Arquivo index.html é criado automaticamente

A EC2 baixa atualizações via NAT Gateway

A página é servida localmente (porta 80)

Acesso via SSM permite validação segura

O bucket S3 também é provisionado para servir conteúdo estático

🧠 5. O que este projeto demonstra

✔️ Conhecimento real de VPC e redes AWS
✔️ Infraestrutura como código (IaC) bem estruturada
✔️ Sub-rede pública × privada
✔️ NAT Gateway + tráfego de saída
✔️ EC2 privada com SSM (sem SSH)
✔️ Segurança mínima e boas práticas
✔️ Automação com UserData
✔️ Criação de aplicação via CloudFormation
✔️ Arquitetura limpa e reutilizável



📬 Contato:

Cauã Freire
📧 [cauafreirealves1@gmail.com]
🔗 LinkedIn: [www.linkedin.com/in/cauafreirealves]
