# Guia do Jogador — Sistema de Pagamentos PIX

©️**Credits: Criado por Bhoske (github: brunohoske)**

Bem-vindo ao guia de pagamentos do servidor! O sistema de PIX permite que você compre itens, kits e benefícios diretamente no jogo usando **PIX** — sem sair do Minecraft. O pagamento é processado pelo Mercado Pago e a entrega é automática.

---

## Sumário

- [Como abrir a loja](#como-abrir-a-loja)
- [Navegando pela loja](#navegando-pela-loja)
- [Realizando uma compra](#realizando-uma-compra)
- [O QR Code no mapa](#o-qr-code-no-mapa)
- [Após o pagamento](#após-o-pagamento)
- [Pedido expirado](#pedido-expirado)
- [Regras e avisos importantes](#regras-e-avisos-importantes)
- [Perguntas frequentes](#perguntas-frequentes)

---

## Como abrir a loja

Use qualquer um dos comandos abaixo para abrir o menu da loja:

```
/loja
```

Aliases (todos fazem a mesma coisa):

```
/shop
/comprar
/pix
```

---

## Navegando pela loja

Ao abrir a loja, você verá o menu principal com as **categorias de produtos** disponíveis.

### Passo 1 — Escolher uma categoria

Clique em uma categoria para ver os produtos disponíveis nela.

### Passo 2 — Escolher um produto

Dentro da categoria, cada item exibe:

- **Nome** do produto
- **Descrição** do que você vai receber
- **Preço** em reais (R$)

Clique no produto desejado para prosseguir.

### Passo 3 — Escolher o método de pagamento

Você verá a tela de gateway de pagamento. Clique em **Mercado Pago** para gerar o PIX.

---

## Realizando uma compra

Após clicar em **Mercado Pago**, o sistema irá:

1. Verificar se você já tem um pedido em andamento
2. Verificar se seu inventário está limpo (em produtos que exigem isso)
3. Criar o seu pedido e gerar o código PIX junto ao Mercado Pago
4. Renderizar o QR Code em um mapa e colocá-lo na sua mão
5. Enviar um link clicável no chat para pagar pelo celular

### ❗ Atenção — inventário limpo

Alguns produtos exigem que o seu inventário esteja **completamente vazio** antes da compra. Se o inventário não estiver limpo, você receberá a mensagem:

> *Seu inventário deve estar limpo para fazer um pedido.*

Esvazie o inventário e tente novamente.

### ❗ Atenção — pedido em andamento

Você só pode ter **um pedido ativo por vez**. Se já tiver um pedido pendente, você verá:

> *Você já possui um pedido em andamento.*

Aguarde o seu pedido atual expirar ou ser pago antes de iniciar um novo.

---

## O QR Code no mapa

Quando o pedido é gerado com sucesso, um **mapa com o QR Code PIX** aparece na sua mão. Esse mapa é o seu comprovante de pagamento.

### Como pagar

**Opção 1 — QR Code no mapa:**

1. Segure o mapa na mão
2. Use a câmera do celular ou o app do banco para escanear o QR Code exibido na tela do jogo
3. Confirme o pagamento no seu banco

**Opção 2 — Link no chat:**

1. No chat do jogo, aparecerá uma mensagem com o link do pagamento
2. Clique em **AQUI** na mensagem para abrir o link no navegador
3. Escaneie o QR Code pelo site ou copie o código PIX

### Prazo para pagamento

Você tem **15 minutos** para efetuar o pagamento após gerar o QR Code. Após esse prazo, o pedido expira automaticamente.

> O sistema verifica o status do pagamento a cada **60 segundos** automaticamente — você não precisa fazer nada após pagar.

---

## Após o pagamento

Assim que o pagamento for confirmado pelo Mercado Pago, o servidor irá:

1. Remover o mapa do QR Code do seu inventário
2. Tocar um som de confirmação
3. Exibir um título na tela:

   > **PEDIDO ENTREGUE**
   > *O seu pedido foi entregue com sucesso!*

4. Enviar uma mensagem no chat confirmando a entrega
5. Executar os comandos de recompensa (itens, permissões, etc.)
6. Devolver o item que estava na sua mão antes da compra

Tudo é automático — não é necessário abrir ticket nem contatar a staff.

---

## Pedido expirado

Se o tempo de **15 minutos** passar sem que o pagamento seja realizado, o pedido expirará automaticamente. Você será notificado com:

- Um som de bloco quebrando
- Título na tela:

  > **PEDIDO EXPIRADO**
  > *O seu pedido EXPIROU!*

- Mensagem no chat informando o vencimento

Após a expiração, você pode iniciar uma nova compra normalmente.

---

## Regras e avisos importantes

### ❗⚠️ IMPORTANTE❗❗❗❗

- **Não reembolsamos pagamentos por erro do jogador.** Leia com atenção o produto antes de pagar.
- O pagamento é feito em **reais (R$)** através do Mercado Pago. Certifique-se de ter saldo disponível.
- **Não feche o jogo** enquanto o pedido estiver pendente — o QR Code pode ser perdido.
- O QR Code é **pessoal e intransferível** — cada código é gerado para um pedido específico.
- Em caso de pagamento confirmado pelo banco mas sem entrega no jogo, abra um ticket na staff informando o **ID do pedido** (visível no link de pagamento).

---

## Perguntas frequentes

**P: Posso ter mais de um pedido ao mesmo tempo?**
R: Não. O sistema permite apenas um pedido ativo por jogador. Aguarde o pagamento ou a expiração para fazer um novo.

---

**P: O QR Code sumiu do meu inventário, o que faço?**
R: Use o link que foi enviado no chat para pagar. Se não encontrar mais o link, aguarde o pedido expirar e tente novamente.

---

**P: Paguei mas não recebi os itens. O que fazer?**
R: O sistema verifica o pagamento a cada 60 segundos. Aguarde até 2 minutos. Se ainda não receber, abra um ticket para a staff com o comprovante do pagamento.

---

**P: Posso cancelar um pedido?**
R: Não há como cancelar manualmente. O pedido expira automaticamente após um periodo. Se já pagou e quer reembolso, entre em contato com a staff.

---

**P: O pagamento tem alguma taxa?**
R: O preço exibido no produto já é o valor final. Uma pequena taxa de processamento (0,99%) é adicionada automaticamente pelo sistema.

---

**P: Quais métodos de pagamento são aceitos?**
R: Apenas **PIX** via Mercado Pago. Cartão de crédito, débito e boleto não são suportados.

---

**P: Como sei se o servidor recebeu meu pagamento?**
R: Você receberá o título **"PEDIDO ENTREGUE"** na tela e os itens serão entregues automaticamente. Se recebeu a notificação de entrega, o pagamento foi confirmado.
