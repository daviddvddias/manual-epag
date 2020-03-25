Acesso as APIs do ePAG
**********************

As operações disponíveis estão descritas nos seguintes endereços abaixo:
########################################################################

Swagger ePAG:
- Sem link ainda.

Manual oficial:
- https://v-epag.estaleiro.serpro.gov.br/simulador/#/pages/api

.. important::
   Os métodos das APIs necessitam autenticação para uso.
   A solicitação das credenciais de acesso para uso das APIs devem ser geradas no SISGRU
   pelo próprio gestor do serviço. No sistema deve ser acessado o item **Meios de Pagamento**, opção **Autorização de uso do ePag.Gov**.

Deve-se usar o cabeçalho http **Authorization: Bearer <token_jwt>** em Base64 para passar as credenciais de autenticação nas chamadas das APIs.

Deve-se usar o cabeçalho http **Content-Type: application/json** ao chamar os endpoints.

Caso deseje você pode utilizar a página https://jwt.io/ para decodificar e codificar o token em Base64.

Valores a preencher
###################

Solicitação de pagamento
------------------------

O método Solicitação de Pagamento éum serviço que permite que sejam 
solicitado um pagamento. Esse método não realiza o pagamento mas solicita uma URL para que o cidadão escolha o método de pagamento.

.. note::
   Esse é um método **POST** e necessita de uma autorização para seu uso.

Parâmetros de Entrada
++++++++++++++++++++++

.. code-block:: json

   {
     "codigoServico": "81",
     "referencia": "123",
     "competencia": "112019",
     "vencimento": "06112019",
     "cnpjCpf": "00000000000191",
     "nomeContribuinte": "EMPRESA FICTÍCIA",
     "valorPrincipal": "100",
     "valorDescontos": "0",
     "valorOutrasDeducoes": "0",
     "valorMulta": "0",
     "valorJuros": "0",
     "valorOutrosAcrescimos": "0",
     "modoNavegacao": "1",
     "urlRetorno": "https://www.example.com/meu_retorno"
   } 

codigoServico
   Informe o código do serviço cadastrado no SISGRU. 

.. note::
    Esse código do serviço não é o mesmo do portal https://gov.br/

referencia
   Valor gerado pelo cliente para referência futura ao pagamento. Não é o mesmo que o número da GRU. 

competencia
   MMAAAA da competência do pagamento.

vencimento
   DDMMAAAA da data de vencimento do pagamento.

cnpjCpf
   CNPJ ou CPF referente ao pagamento.

nomeContribuinte
   Nome do contribuinte. Pode ser o nome da empresa.

valorPrincial
   Valor principal do pagamento

valorDescontos
   Valor de desconto do pagamento.

valorOutrasDeducoes
   Valor de outras deduções do pagamento.

valorMulta
   Valor de multa do pagamento.

valorJuros
   Valor de juros do pagamento.

valorOutrosAcrescimos
   Valor de outros acrescimos do pagamento.

modoNavegacao
   Modo de navegação que será exibido ao cidadão. Valores possíveis de 1 e 2.
   1 – Abrir a página do banco para débito online na mesma aba do sistema cliente (valor padrão, caso o parâmetro não seja enviado).
   2 – Abrir a página do banco para débito online numa nova aba do navegador. 

urlRetorno
   URL do sistema cliente para onde o usuário irá retornar ao selecionar a opção Concluir na tela de confirmação de pagamento do PagTesouro (necessário quando "modoNavegacao": "1"). 

Por favor verificar o manual em https://v-epag.estaleiro.serpro.gov.br/simulador/#/pages/api para outras considerações.

