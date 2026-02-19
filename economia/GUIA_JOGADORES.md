# Guia do Jogador — Sistema de Economia

Bem-vindo ao servidor! Este guia explica tudo que você precisa saber sobre o sistema de economia: seu saldo, as lojas de baú, negócios, empregos e dívidas.

---

## Sumário

- [Saldo e Pagamentos](#saldo-e-pagamentos)
- [Lojas de Baú (Chest Shops)](#lojas-de-baú-chest-shops)
- [Negócios e Empregos](#negócios-e-empregos)
- [Salários e Atrasos](#salários-e-atrasos)
- [Dívidas](#dívidas)
- [Histórico de Movimentações](#histórico-de-movimentações)
- [Seus Limites](#seus-limites)

---

## Saldo e Pagamentos

### Ver seu saldo

```
/bal
```

Para ver o saldo de outro jogador:

```
/bal <jogador>
```

### Ranking de saldos

```
/baltop
```

### Pagar outro jogador

```
/pay <jogador> <valor>
```

Exemplo: `/pay Steve 50` envia $50,00 para Steve.

---

## Lojas de Baú (Chest Shops)

As lojas funcionam com **placas escritas sobre ou ao lado de um baú**. Basta clicar com o botão direito na placa para comprar ou vender.

### Como interagir com uma loja

| Ação | O que acontece |
|---|---|
| **Botão direito** na placa | Executa a transação (compra ou venda) |
| **Shift + botão direito** na placa | Exibe informações da loja sem comprar nada |

---

### Tipos de loja

#### Loja `[buy]` — Você compra do baú do dono

O dono da loja abastece um baú com itens e coloca uma placa com o preço. Você clica para comprar.

**Exemplo de placa:**
```
[buy]
Diamantes
10$
minecraft:diamond 1
```

- O dinheiro sai da sua conta e vai para o dono
- O item sai do baú e vai para o seu inventário
- Se o baú estiver vazio, a compra não é realizada

#### Loja `[sell]` — Você vende para o baú do dono

O dono da loja paga para receber itens. Você segura o item na **mão principal** e clica na placa para vender.

**Exemplo de placa:**
```
[sell]
Comprando diamantes
8$
minecraft:diamond 1
```

- Segure **exatamente** a quantidade indicada na mão principal
- O item sai da sua mão e vai para o baú
- O dinheiro sai da conta do dono e vai para a sua
- Se o baú estiver cheio ou o dono sem saldo, a venda não é realizada

#### Loja `[server-buy]` — Loja do servidor (você compra)

O servidor vende itens sem precisar de baú físico. Funciona igual ao `[buy]`, mas o estoque é infinito.

**Exemplo de placa:**
```
[server-buy]
Kit Diamantes
50$
minecraft:diamond 5
```

- Você paga e recebe o item diretamente no inventário

#### Loja `[server-sell]` — Loja do servidor (você vende)

O servidor compra seus itens. Segure o item na mão principal e clique.

**Exemplo de placa:**
```
[server-sell]
Venda Diamantes
6$
minecraft:diamond 1
```

- O item sai da sua mão e o dinheiro entra na sua conta

---

### Como criar uma loja `[buy]` ou `[sell]`

1. Coloque um **baú** onde quiser
2. Coloque uma **placa** em cima do baú (ou na parede ao lado)
3. Escreva as 4 linhas no formato correto:
   - Linha 1: `[buy]` ou `[sell]`
   - Linha 2: Descrição livre (ex: `Diamantes`)
   - Linha 3: Preço (ex: `10$`)
   - Linha 4: ID do item e quantidade (ex: `minecraft:diamond 1`)
4. Confirme a placa — ela será registrada como loja automaticamente

> O baú precisa estar diretamente abaixo ou atrás da placa (caso seja placa de parede).

---

## Negócios e Empregos

### Criar um negócio

```
/job create <nome>
```

Exemplo: `/job create padaria`

Aparecerá uma mensagem de confirmação com o custo de abertura (se configurado pelo servidor). Clique em **[CONFIRMAR]** para criar.

> Você precisa ter saldo suficiente para pagar a taxa de abertura, se houver. Não é criada dívida para isso.

---

### Ver seus negócios

```
/job myBusiness list
```

Exibe todos os seus negócios e quantos empregados cada um tem.

---

### Contratar um jogador

```
/job contratar <negocio> <jogador> <salario> <frequencia>
```

- `<negocio>` — nome do seu negócio (autocomplete disponível)
- `<jogador>` — nome do jogador (deve estar online)
- `<salario>` — valor do salário por período
- `<frequencia>` — `diario`, `semanal` ou `mensal`

Exemplo: `/job contratar padaria Steve 100 semanal`

O jogador receberá um convite no chat e terá **60 segundos** para aceitar ou recusar.

---

### Aceitar ou recusar um convite de emprego

Ao receber um convite, clique em **[ACEITAR]** ou **[RECUSAR]** no chat.

Ou use os comandos:

```
/job aceitar
/job recusar
```

---

### Ver seus empregos

```
/job myJobs list
```

Exibe todos os seus contratos de trabalho ativos, com o nome do negócio, empregador, salário e frequência.

---

### Ver detalhes de um emprego

```
/job myJobs <empregador> <negocio> info
```

Exibe o salário, frequência e a **data do próximo pagamento**.

---

### Pedir demissão

```
/job myJobs <empregador> <negocio> sair
```

Aparecerá uma confirmação. Clique em **[CONFIRMAR DEMISSÃO]** para sair.

> Ao pedir demissão você **não recebe indenização**. Indenização só é paga quando o dono fecha o negócio.

---

### Fechar um negócio

```
/job fechar <negocio>
```

Aparecerá um resumo com o número de empregados, o total de indenizações e a multa por encerramento. Clique em **[CONFIRMAR ENCERRAMENTO]** para prosseguir.

Ao fechar:
- Cada empregado recebe uma indenização equivalente a um período de salário
- Uma multa de encerramento é cobrada do dono
- Se o dono não tiver saldo suficiente, os valores viram dívida

---

## Salários e Atrasos

Os salários são pagos automaticamente pelo servidor conforme a frequência configurada no contrato (`diario`, `semanal`, `mensal`).

Se o empregador **não tiver saldo suficiente** no momento do pagamento:
- O sistema paga o que for possível imediatamente
- O restante é registrado como **dívida de salário**
- Tanto o empregado quanto o empregador são notificados

### Ver seus atrasos de salário

```
/salario atrasos
```

Exibe todos os salários que você tem a receber, por negócio e valor total pendente.

---

## Dívidas

Dívidas são geradas automaticamente quando alguém não tem saldo suficiente para pagar taxas, salários ou indenizações.

Elas são **quitadas automaticamente** sempre que dinheiro entra na sua conta — o sistema desconta o que for possível e avisa você no chat.

### Ver suas dívidas

```
/dividas list
```

Exibe o tipo de dívida, o credor, o valor e a data em que foi gerada.

**Tipos de dívida:**

| Tipo | Origem |
|---|---|
| `salario` | Salário que você (como empregador) não conseguiu pagar |
| `taxa` | Imposto que você não conseguiu pagar integralmente |
| `indenizacao` | Indenização ao fechar um negócio sem saldo suficiente |

---

## Histórico de Movimentações

Toda movimentação financeira é registrada. Você pode consultar seu histórico com:

```
/historico
```

Para filtrar por tipo:

```
/historico <tipo>
```

**Tipos disponíveis:** `pay` · `salario` · `taxa` · `divida` · `indenizacao` · `multa` · `compra` · `venda`

O histórico exibe os **15 registros mais recentes** de cada consulta.

---

## Seus Limites

Dependendo do seu grupo no servidor, você pode ter limites de negócios e empregos. Para ver seus limites atuais e quanto você já está usando:

```
/jobinfo
```

**Exemplo de saída:**
```
=== Seus Limites de Trabalho ===
Grupo: vip
Negócios (criados por você): 1 / 3
Empregos (você como empregado): 0 / 3
Empregados (total nos seus negócios): 2 / 10
```

| Campo | O que significa |
|---|---|
| **Negócios** | Quantos negócios você criou vs. o máximo permitido |
| **Empregos** | Quantos empregos você tem como funcionário vs. o máximo |
| **Empregados** | Total de funcionários em todos os seus negócios vs. o máximo |
