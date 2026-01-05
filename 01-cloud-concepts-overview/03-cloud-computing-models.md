# Modelos de Computação em Nuvem

Para a prova, você precisa saber a diferença de **responsabilidade** e **controle** entre os três modelos principais.

---

## 1. IaaS: Infrastructure as a Service (Infraestrutura como Serviço)
É o modelo base. Contém os blocos de construção fundamentais da TI em nuvem.
* **O que é:** Você aluga a infraestrutura (servidores físicos e virtuais, rede, armazenamento) e gerencia o sistema operacional para cima.
* **Nível de Controle:** **O Mais Alto**. Você tem flexibilidade total, mas também mais responsabilidade.
* **Quem gerencia o quê:**
    * **AWS:** Gerencia a infra física (Data Centers, Hardware, Rede).
    * **Você:** Gerencia o Sistema Operacional, patches, dados e aplicações.
* **Exemplos AWS:** Amazon EC2, Amazon VPC.

## 2. PaaS: Platform as a Service (Plataforma como Serviço)
Focado em desenvolvedores que não querem lidar com servidores.
* **O que é:** A AWS fornece uma plataforma pronta (com SO e banco de dados já instalados) para você apenas implantar seu código.
* **Nível de Controle:** Médio. Você perde acesso direto ao SO, mas ganha velocidade.
* **Quem gerencia o quê:**
    * **AWS:** Gerencia a infra física + Sistema Operacional + Correções (patches) de software.
    * **Você:** Foca apenas no desenvolvimento e implantação da aplicação.
* **Exemplos AWS:** AWS Elastic Beanstalk, Amazon RDS (Relational Database Service).

## 3. SaaS: Software as a Service (Software como Serviço)
Produto finalizado.
* **O que é:** Um software completo executado e gerenciado pelo provedor. Você apenas o utiliza.
* **Nível de Controle:** Baixo (ou Nenhum). Você não sabe onde está rodando, só acessa.
* **Exemplos Gerais:** Gmail, Dropbox, Zoom.
* **Exemplos AWS:** Amazon Connect (Call Center na nuvem), Amazon Chime.

---

## A Analogia da "Pizza as a Service"
Esta analogia clássica ajuda a memorizar quem faz o quê:

| Modelo | Analogia | Explicação |
| :--- | :--- | :--- |
| **On-Premises** | **Feita em Casa** | Você compra os ingredientes, faz a massa, assa, serve e lava a louça. (Você faz tudo). |
| **IaaS** | **"Take and Bake"** | Você compra a pizza montada (infra), mas usa seu próprio forno e mesa. (AWS dá o hardware, você configura o SO). |
| **PaaS** | **Delivery** | A pizza chega pronta e quente. Você só precisa arrumar a mesa e comer. (AWS entrega o ambiente pronto, você põe o código). |
| **SaaS** | **Restaurante** | Você vai ao local, come e paga. Não se preocupa com forno, mesa ou louça. (Tudo gerenciado pelo provedor). |

---

## Resumo Visual de Responsabilidade

| Gerenciamento | IaaS (Ex: EC2) | PaaS (Ex: Elastic Beanstalk) | SaaS (Ex: Gmail) |
| :--- | :--- | :--- | :--- |
| **Aplicações** | 👤 Você | 👤 Você | ☁️ AWS |
| **Dados** | 👤 Você | 👤 Você | ☁️ AWS |
| **Runtime / Middleware** | 👤 Você | ☁️ AWS | ☁️ AWS |
| **Sistema Operacional (OS)** | 👤 Você | ☁️ AWS | ☁️ AWS |
| **Virtualização/Servidores** | ☁️ AWS | ☁️ AWS | ☁️ AWS |
| **Rede/Armazenamento** | ☁️ AWS | ☁️ AWS | ☁️ AWS |
