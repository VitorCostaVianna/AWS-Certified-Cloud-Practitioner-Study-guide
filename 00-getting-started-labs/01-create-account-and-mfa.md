# Lab 01: Criar Conta e Configurar MFA (Segurança Essencial)

## Objetivo
Criar sua conta na AWS aproveitando o nível gratuito (Free Tier) e proteger o "Usuário Raiz" (Root User), que tem poderes ilimitados.

---

## Parte 1: Criar a Conta AWS Free Tier
O "Free Tier" (Nível Gratuito) permite que você use diversos serviços de graça por 12 meses (dentro de certos limites).

### Pré-requisitos
* Um endereço de e-mail válido.
* Um cartão de crédito ou débito (para verificação de identidade, mesmo que não haja cobrança imediata).
* Um número de telemóvel para verificação via SMS.

### Passo a Passo
1. Aceda a [https://aws.amazon.com/free](https://aws.amazon.com/free).
2. Clique em **"Create a Free Account"** (Criar uma conta gratuita).
3. **Email e Nome:** Insira o seu email e escolha um nome para a conta (ex: "MyStudyAccount").
4. **Verificação:** Siga os passos para verificar o email e adicione as informações de pagamento.
    * *Nota:* A AWS fará uma cobrança temporária de $1 USD (aprox.) apenas para validar o cartão, que será estornada.
5. **Verificação de Identidade:** Receba o SMS ou chamada para confirmar o seu telefone.
6. **Plano de Suporte:** Escolha **"Basic Support - Free"** (Suporte Básico).
    * *Dica de Prova:* O suporte básico é gratuito para todos os clientes, mas não dá acesso a suporte técnico por chat/telefone (apenas para questões de faturação).

---

## Parte 2: Configurar MFA no Usuário Raiz (Crítico!)
O utilizador que cria a conta é chamado de **Root User** (Utilizador Raiz). Ele tem acesso ilimitado e **não pode ser restrito**. Se alguém roubar esta senha, pode apagar tudo ou minerar bitcoins na sua conta.

**Regra de Ouro para a Prova:** A primeira tarefa após criar a conta é ativar a Autenticação Multifator (MFA) no Root User.

### Passo a Passo
1. Inicie sessão na AWS Console usando o seu email e senha (selecione "Root user").
2. No canto superior direito, clique no nome da sua conta e selecione **"Security Credentials"** (Credenciais de segurança).
3. Procure a secção **"Multi-factor authentication (MFA)"**.
4. Clique em **"Assign MFA"** (Atribuir MFA).
5. Escolha um nome para o dispositivo (ex: `MeuTelemovel`).
6. Selecione **"Authenticator app"** (Google Authenticator, Microsoft Authenticator, Authy, etc.).
7. Clique em **Next**.
8. **No seu telemóvel:** Abra a app autenticadora e leia o código QR apresentado no ecrã.
9. **Na AWS:**
    * Digite o **MFA code 1**: O código que aparece agora na app.
    * Aguarde o código mudar (aprox. 30 segundos).
    * Digite o **MFA code 2**: O novo código que apareceu.
10. Clique em **"Add MFA"**.

✅ **Sucesso!** Agora, sempre que fizer login como Root, precisará da senha + o código do telemóvel.

---

## Parte 3: Criar um Alerta de Orçamento (Budget)
Para evitar surpresas no cartão de crédito se passar os limites do Free Tier.

1. Na barra de pesquisa no topo, digite **"Budgets"** e clique no serviço.
2. Clique em **"Create budget"**.
3. Selecione **"Use a template (simplified)"**.
4. Escolha **"Zero spend budget"** (Orçamento de gasto zero).
    * Isso enviará um email se a sua conta gastar mais de $0.01 (ou seja, se sair do nível gratuito).
5. Insira o seu email em "Email recipients".
6. Clique em **"Create budget"**.

---

### Resumo para o Exame (CCP)
* **Root User:** Tem acesso total. Deve ser protegido com MFA e **NÃO** deve ser usado para tarefas diárias.
* **MFA (Multi-Factor Authentication):** Algo que você sabe (senha) + Algo que você tem (token/app). É a melhor prática de segurança simples.
* **AWS Budgets:** Ferramenta para monitorizar custos e enviar alertas (pode ser configurado para alertar *antes* de estourar o limite).
