<!-- ![alt text](https://github.com/UZEcartoes/ecommerce/blob/main/imagemTeste.png?raw=true) -->

# Integração E-Commerce

A integração e-commerce pode ser feitas de duas formas : 

- Via POS
- Via SOAP 

Estes dois modos de integração serão tratados neste artigo. Cada um deles de modo detalhado a fim de facilitar o entendimento dos gerentes a respeito dos meios de inegração e auxiliar os programadores na compreensão da parte técnica.

# - Via POS

Este método é o que requer menos esforço de implementação e consiste basicamente no pagamento da compra na hora da retirada dos produtos(modalidade pós pago).
É preciso parametrizar esta opção no módulo de administrador do sistema como sendo uma das formas de pagamento que serão exibidas no front-end para os clientes no momento do checkout. 

- O cliente faz a escolha dos produtos no site
- Seleciona a opção de pagar utilizando o cartão da empresa
- Na hora de retirar o produto o cliente efetua o pagamento na máquina

https://user-images.githubusercontent.com/screenshotMercado.png

Ao invés de ser debitada a compra no cartão na hora da compra via e-commerce, ela é debitada na máquina na retirada do produto.

# - Via SOAP

O SOAP é o protocolo utilizado pela BIZ para que sejam efetuadas as transações que são feitas com os cartões da UZE.

Dentro dos serviços disponíveis, o que utilizaremos no e-commerce são : 
- Compra - Este serviço deverá ser utilizado para gerar transações financeiras de compra e pagamento.
- Confirma Compra - Este serviço deverá ser utilizado para gerar uma confirmação de uma transação Financeira de Compra ou Pagamento.
- Cancelamento Compra - Este serviço deverá ser utilizado para gerar uma transação de cancelamento de Compra e Pagamento, onde os tipos são definidos pelo campo p_codproc.
- Desfazimento Transação - Este serviço deverá ser utilizado para gerar uma transação de desfazer uma Compra/Pagamento, com também  desfazer  um  Cancelamento  de  Compra/Pagamento,onde  os  tipos  de  são  definidos pelo campo p_codproc.


```
A criação de credenciais, utilização da chave de acesso e criptografia serão explicados no vídeo e na documentação abaixo.
```
https://user-images.githubusercontent.com/86687737/123870897-5f325800-d909-11eb-8249-56df5990814f.mp4


- Link da documentação : [esp_interface_autorizacao_webservice_v1_5 nova.pdf](https://github.com/UZEcartoes/ecommerce/files/6736735/esp_interface_autorizacao_webservice_v1_5.nova.pdf)


# Dúvidas

Para o caso de dúvidas entre em contato conosco através do link abaixo : 
- < LINK DO PIPEFY > 
