# Modelos de Implantação e AWS CAF

## Parte 1: Modelos de Implantação (Deployment Models)

Existem três maneiras principais de implantar recursos na nuvem. A escolha depende de regulação, custo e necessidades técnicas.

### 1. Nuvem Pública (Public Cloud / Cloud-Native)
Este é o modelo padrão da AWS.
* **O que é:** A aplicação reside 100% na infraestrutura do provedor (AWS). Você não possui servidores físicos.
* **Como funciona:**
    * *Novas Aplicações:* Criadas diretamente na nuvem ("Cloud Native").
    * *Migrações:* Aplicações antigas movidas do data center para a AWS.
* **Vantagem Principal:** Você não gerencia hardware (No CapEx) e aproveita elasticidade total.

### 2. Híbrida (Hybrid)
O "meio-termo" que conecta os dois mundos.
* **O que é:** Uma conexão direta (via VPN ou Direct Connect) entre a nuvem pública e o seu data center local.
* **Caso de Uso:** Bancos ou governos que precisam manter dados sensíveis em casa por lei, mas querem usar a nuvem para o front-end ou análise de dados.
* **Vantagem Principal:** Flexibilidade para expandir gradualmente sem descartar o investimento feito em hardware local.

### 3. No Local (On-Premises / Private Cloud)
O modelo tradicional com "roupagem" moderna.
* **O que é:** A empresa é dona de tudo (prédio, servidores, segurança). Tudo roda "dentro de casa".
* **Conceito de Nuvem Privada:** É quando você usa virtualização (VMware, Hyper-V) para imitar a nuvem pública, mas usando seu próprio hardware.
* **Vantagem Principal:** Controle total sobre a localização dos dados.
* **Desvantagem:** Alto custo operacional e de manutenção (CapEx alto).

---

## Parte 2: AWS Cloud Adoption Framework (CAF)

O **AWS CAF** é um guia para ajudar organizações a migrar para a nuvem de forma rápida e eficiente. Ele organiza essa jornada em **6 Perspectivas**.

> **Para a prova:** Você precisa saber quais perspectivas são focadas em **Negócios** e quais são focadas em **Tecnologia**.

### Grupo 1: Capacidades de Negócios (Não-Técnico)
Focam em garantir que a nuvem gere valor e que as pessoas estejam preparadas.

| Perspectiva | Foco Principal | Perguntas que resolve |
| :--- | :--- | :--- |
| **1. Negócios** (Business) | **Resultados e Estratégia** | "Como a nuvem vai nos dar lucro ou economizar dinheiro?" Garante que a TI esteja alinhada aos objetivos da empresa. |
| **2. Pessoas** (People) | **RH e Treinamento** | "Quem precisa ser contratado ou treinado?" Foca em cultura organizacional, gestão de mudança e *skills* da equipe. |
| **3. Governança** (Governance) | **Priorização e Controle** | "Quais são as regras?" Foca em gerenciar o portfólio de projetos, medir resultados e garantir conformidade. |

### Grupo 2: Capacidades Técnicas
Focam na implementação real da nuvem.

| Perspectiva | Foco Principal | Perguntas que resolve |
| :--- | :--- | :--- |
| **4. Plataforma** (Platform) | **Arquitetura e Design** | "Como vamos desenhar a solução?" Foca na estrutura técnica, padrões de arquitetura e ferramentas. |
| **5. Segurança** (Security) | **Compliance e Proteção** | "Como protegemos os dados?" Foca em IAM (permissões), controle de dados e conformidade com leis. |
| **6. Operações** (Operations) | **Dia a dia e Saúde** | "Como mantemos isso rodando?" Foca em monitoramento, recuperação de desastres e saúde do sistema. |
