# Lab 03: Desafio da Latência (EC2 Global)

## 🎯 Objetivo
Criar duas instâncias EC2 (uma na Virgínia/EUA e outra em São Paulo/BR) e testar o tempo de resposta (ping) da sua casa até elas.

* **Tempo estimado:** 15-20 minutos.
* **Custo:** Alguns centavos de dólar (se você encerrar as instâncias logo depois).
* **Atenção:** A região de São Paulo costuma ser mais cara, mas para um teste de minutos o custo é irrisório.

---

## Parte 1: Lançando a Máquina nos EUA (us-east-1)

1.  Faça login no **AWS Management Console**.
2.  No canto superior direito (Menu Global), verifique se a região está **N. Virginia (us-east-1)**.
3.  Vá para o serviço **EC2**.
4.  Clique no botão laranja **Launch Instance** (Executar instância).
5.  **Configurações:**
    * **Name:** `Servidor-EUA`
    * **OS Images:** Escolha **Amazon Linux** (é leve e rápido).
    * **Instance Type:** `t2.micro` ou `t3.micro` (Geralmente Free Tier elegível).
    * **Key Pair:** Selecione **"Proceed without a key pair"** (Continuar sem par de chaves). *Não vamos precisar logar na máquina, apenas "pingar" nela.*
    * **Network Settings (Importante):**
        * Em "Firewall (security groups)", deixe em **Create security group**.
        * *Nota:* Por padrão, ele libera apenas SSH (porta 22). Vamos liberar o Ping depois.
6.  Clique em **Launch Instance**.

---

## Parte 2: Lançando a Máquina no Brasil (sa-east-1)

1.  No canto superior direito, mude a região para **South America (São Paulo) / sa-east-1**.
2.  Repita os mesmos passos da Parte 1, mas com atenção:
    * **Name:** `Servidor-BR`
    * **OS Images:** Amazon Linux.
    * **Network Settings:** Crie um **novo** security group.
        * *Conceito de Prova:* Security Groups são **regionais**. O grupo que você criou nos EUA não existe aqui.
3.  Clique em **Launch Instance**.

---

## Parte 3: O "Pulo do Gato" (Liberando o Ping)

Se você tentar pingar agora, vai falhar. A AWS bloqueia o protocolo ICMP (Ping) por padrão. O Security Group funciona como um firewall "deny-all" (bloqueia tudo que não for explicitamente permitido).

**Repita este processo para AMBAS as instâncias (mude de região para fazer em cada uma):**

1.  No painel EC2, clique em **Instances** e selecione sua instância.
2.  Na aba inferior, clique em **Security** (Segurança).
3.  Clique no link azul do **Security Group** (algo como `sg-0abc123...`).
4.  Clique em **Edit inbound rules** (Editar regras de entrada).
5.  Clique em **Add rule**.
    * **Type:** Procure por **All ICMP - IPv4**. (Isso é o Ping).
    * **Source:** Selecione **Anywhere-IPv4** (`0.0.0.0/0`).
6.  Clique em **Save rules**.

### ⚠️ Solução de Problemas Comuns
> **Erro:** "The security group 'sg-xyz' does not exist"
>
> **Causa:** Você está tentando editar um Security Group criado nos EUA enquanto o console está na região do Brasil (ou vice-versa).
> **Solução:** Mude a região no menu superior para corresponder à instância.

---

## Parte 4: O Teste de Latência 🚀

Agora vamos ver a física em ação (a luz viajando pela fibra óptica).

1.  Anote o **Public IPv4 address** da instância dos EUA.
2.  Anote o **Public IPv4 address** da instância do Brasil.
3.  Abra o terminal do seu computador (CMD, PowerShell ou Terminal).

### Teste 1: Viajando até os EUA
Digite:
```bash
ping <IP-DO-EUA>
# Exemplo: ping 54.123.45.67

# Para testar Brasil
ping <IP-DO-BRASIL>
```

### Resultados e Evidências
Aqui estão os prints comparando a latência entre as duas regiões a partir da minha localização.

Observe o tempo de resposta (time=XXms). Deve ser mais alto devido à distância física.

<img width="542" height="500" alt="image" src="https://github.com/user-attachments/assets/f6ae43dd-6f8b-421e-aa2a-2ca3101db21e" />

### Parte 5: Limpeza (Essencial!)
Para garantir que não haverá cobranças futuras:

Vá no console EC2 das duas regiões (N. Virginia e São Paulo).

Selecione a instância criada.

Clique em Instance State > Terminate Instance (Encerrar).

### Nota de Prova:

Stop: Apenas desliga a máquina. Você para de pagar por CPU, mas continua pagando pelo disco (EBS).

Terminate: Apaga a máquina e o disco. A cobrança para totalmente.

#### Latência é Física: Escolher a região correta é vital para a experiência do usuário. Se seus clientes estão no Brasil, use sa-east-1 para baixa latência.
