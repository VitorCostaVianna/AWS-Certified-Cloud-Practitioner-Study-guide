# Exemplo de Pergunta do Exame: Economia da Nuvem

## A Pergunta
**Por que a AWS é mais econômica do que data centers tradicionais para aplicações com workloads de computação variáveis?**

A) Os custos do Amazon Elastic Compute Cloud (Amazon EC2) são cobrados mensalmente.

B) Os clientes mantêm o acesso administrativo completo às instâncias do Amazon EC2 deles.

C) As instâncias do Amazon EC2 podem ser executadas sob demanda quando necessário.

D) Os clientes podem executar instâncias suficientes permanentemente para lidar com picos de workload.

---

## A Resposta
✅ **Resposta Correta: C**
> "As instâncias do Amazon EC2 podem ser executadas sob demanda quando necessário."

### Por que esta é a resposta correta?
A palavra-chave na pergunta é **"workloads de computação variáveis"**.
* Se você tem um pico de acesso (ex: Black Friday) e depois o acesso cai, um data center tradicional exigiria que você comprasse servidores suficientes para o pico, que ficariam ociosos (desperdiçando dinheiro) no resto do tempo.
* Na AWS, você pode ligar instâncias **sob demanda** apenas durante o pico e desligá-las depois. Isso elimina o custo da capacidade ociosa.

---

## Análise das Alternativas Incorretas

* **A (Incorreta):** A cobrança do EC2 pode ser por segundo ou hora, não necessariamente mensal. Além disso, a frequência da cobrança não é o que torna a nuvem mais econômica para cargas variáveis, mas sim a *elasticidade*.
* **B (Incorreta):** Ter acesso administrativo é uma funcionalidade de gerenciamento, não uma vantagem econômica direta relacionada a cargas de trabalho variáveis.
* **D (Incorreta):** Executar instâncias *permanentemente* para lidar com picos é exatamente o modelo antigo (provisionamento excessivo). Isso é caro e ineficiente, pois você paga pelos servidores mesmo quando não há tráfego.
