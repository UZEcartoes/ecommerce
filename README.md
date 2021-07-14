<!-- ![alt text](https://github.com/UZEcartoes/ecommerce/blob/main/imagemTeste.png?raw=true) -->

# Integração E-Commerce

A integração e-commerce pode ser feitas de duas formas : 

- Via POS
- Via SOAP 

Estes dois modos de integração serão tratados neste artigo. Cada um deles de modo detalhado a fim de facilitar o entendimento dos gerentes a respeito dos meios de inegração e auxiliar os programadores na compreensão da parte técnica.

# - Via POS

Este método é apenas uma alternativa e requer menos esforço de implementação. O mesmo consiste, basicamente, no pagamento da compra na hora da retirada dos produtos(modalidade pós pago).
É preciso parametrizar esta opção no módulo de administrador do sistema como sendo uma das formas de pagamento que serão exibidas no front-end para os clientes no momento do checkout. 

- O cliente faz a escolha dos produtos no site.
- Seleciona a opção de pagar utilizando o cartão da empresa.
- Na hora de retirar o produto o cliente efetua o pagamento na máquina POS física ou no POS virtual.

<p align="center">
  <img src="screenshotMercado.png">
</p>

Ao invés de ser debitada a compra no cartão na hora da compra via e-commerce, ela é debitada na máquina na retirada do produto.

# - Via SOAP <a href="documentoBiz.pdf">(Documento)</a>

O SOAP é o protocolo utilizado pela BIZ para que sejam efetuadas as transações que são feitas com os cartões da UZE.

Exemplo de fluxo do processo : 

- Cliente seleciona os produtos que deseja. Suponhamos que ele selecionou os seguintes produtos:

<table>
  <tbody>
    <tr>
      <th>Sabão em pó X - R$15,00</th>
      <th align="center">Amaciante Y - R$15,00</th>
      <th align="right">1kg de inhame - R$ 8,00 Kg</th>
    </tr>
  </tbody>
</table>

- O valor total da compra é R$38,00. No momento do checkout, o cliente não sabe quanto vai custar o item a peso, visto que pode não coincidir com o valor exato de 1Kg. Sendo assim, o serviço SOAP para informar a compra deve ser chamado o serviço "Compra", porém com o campo "p_confirmada" igual a 0, ou seja, ficará pendente.

<p align="center">
  <img width="500" src="p_confirmada.png">
</p>

- Será necessário guardar o número p_nsu (Número sequencial único) da transação de origem e todas as demais informações do passo <b>#5 - Compra e Pagamento</b> do documento SOAP. Essas informações serão necessárias para os passos <b>#6 - Confirmação de compra e pagamento</b> e <b>#7 - Cancelamento de compra e pagamento</b>.

- No momento da separação dos produtos e pesagem, o produto a peso, ficou em 980g ao invés de 1Kg conforme solicitado. Neste caso, a compra original deve ser CANCELADA e uma nova compra DEVE SER COMPUTADA.
- Para o cancelamento, siga o passo <b>#7 - Cancelamento de compra e pagamento</b> do documento SOAP.
- Para o cadastramento da nova compra, siga os passos <b>#5</b> e <b>#6</b> do documento SOAP.
<!--
Dentro dos serviços disponíveis, o que utilizaremos no e-commerce são : 
- Compra - Este serviço deverá ser utilizado para gerar transações financeiras de compra e pagamento.
- Confirma Compra - Este serviço deverá ser utilizado para gerar uma confirmação de uma transação Financeira de Compra ou Pagamento.
- Cancelamento Compra - Este serviço deverá ser utilizado para gerar uma transação de cancelamento de Compra e Pagamento, onde os tipos são definidos pelo campo p_codproc.
- Desfazimento Transação - Este serviço deverá ser utilizado para gerar uma transação de desfazer uma Compra/Pagamento, com também  desfazer  um  Cancelamento  de  Compra/Pagamento,onde  os  tipos  de  são  definidos pelo campo p_codproc.

```
A criação de credenciais, utilização da chave de acesso e criptografia serão explicados no vídeo e na documentação abaixo.
```
-->

https://user-images.githubusercontent.com/86687737/123870897-5f325800-d909-11eb-8249-56df5990814f.mp4


- Link da documentação : [Documentacao Biz](documentacaoBiz.pdf)


# Dúvidas

Para o caso de dúvidas entre em contato conosco através do link abaixo : 
- < LINK DO PIPEFY > 
