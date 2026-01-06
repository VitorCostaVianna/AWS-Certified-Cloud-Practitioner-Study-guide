# Lab 02: Tour pelo Console de Gerenciamento da AWS

## Objetivo
Familiarizar-se com a interface web da AWS (Management Console) e entender como alternar entre Regiões, encontrar serviços e acessar ferramentas de linha de comando.

---

## 1. A Tela Inicial (Console Home)
Ao fazer login, você vê a "Console Home". Ela é composta por **Widgets** personalizáveis.
* **Dica:** Você pode arrastar, soltar e redimensionar esses widgets (como "Recently visited", "Cost & usage", "Health").

## 2. A Barra de Navegação Superior (Top Navigation)
Esta barra está sempre visível e contém as ferramentas mais importantes.

### A. Barra de Pesquisa (Unified Search)
No topo (Alt+S).
* **O que faz:** Pesquisa por Serviços (ex: EC2), Recursos (ex: uma instância específica), Documentação, Tutoriais e produtos do Marketplace.
* **Uso na Prova:** Lembre-se que o "Resource Groups & Tag Editor" é uma forma avançada de buscar recursos, mas a barra superior é a navegação rápida.

### B. AWS CloudShell (Ícone do Terminal >_)
Ao lado da barra de pesquisa.
* **O que é:** Um terminal de linha de comando (CLI) gratuito baseado em navegador.
* **Para que serve:** Permite rodar comandos AWS CLI sem precisar instalar nada no seu computador.

---

## 3. O Seletor de Regiões (Region Selector) 🌍
Localizado no **canto superior direito** (ao lado do nome do usuário). **Este é um tópico quente de prova.**



### O Conceito
A AWS tem infraestrutura física espalhada pelo mundo. Ao criar um recurso (como um servidor), você deve escolher **onde** ele vai viver fisicamente.

### Por que escolher uma Região específica? (4 Fatores de Prova)
1.  **Conformidade (Compliance/Data Sovereignty):** Se a lei diz que os dados não podem sair da Alemanha, você DEVE escolher a região de Frankfurt (`eu-central-1`).
2.  **Proximidade (Latência):** Escolha a região mais próxima dos seus clientes para o site carregar rápido (ex: `sa-east-1` em São Paulo para clientes no Brasil).
3.  **Disponibilidade de Serviços:** Nem todos os serviços existem em todas as regiões. Regiões novas têm menos serviços.
4.  **Preço:** O custo varia. Geralmente, `us-east-1` (N. Virginia) é mais barata que `sa-east-1` (São Paulo).

### Serviços Globais vs. Regionais
Observe o seletor de região ao clicar nestes serviços:
* **EC2, Lambda, S3:** O seletor mostra a região (ex: N. Virginia). São serviços **Regionais**.
* **IAM, Route 53, CloudFront:** O seletor muda para **"Global"** e fica cinza. São serviços que não estão presos a um data center específico.

---

## 4. O Menu de Usuário
No canto superior direito (onde está o nome da sua conta).
* **Account ID:** O número de 12 dígitos que identifica sua conta.
* **Security Credentials:** Onde você configura o MFA (visto no Lab 01).
* **Billing and Cost Management:** Onde você vê suas faturas.

---

## 5. Prática Sugerida
1.  **Troque de Região:** Mude de *N. Virginia (us-east-1)* para *São Paulo (sa-east-1)*. Observe que a URL muda.
2.  **Verifique Serviços Globais:** Digite "IAM" na busca e entre no serviço. Veja o seletor de região ficar cinza ("Global").
3.  **Favoritos:** Busque por "EC2". Ao passar o mouse sobre o nome no menu, clique na **Estrela (⭐)**. Ele aparecerá na sua barra de favoritos para acesso rápido.

---

### Resumo para o Exame
* A maioria das configurações na AWS são **Region scoped** (escopo regional). Se você criou uma máquina em SP e não a encontra, verifique se não está logado na região de Virgínia por engano.
* A **seleção da região** é responsabilidade do cliente (Customer Responsibility).
