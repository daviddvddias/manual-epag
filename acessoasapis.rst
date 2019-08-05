Acesso as APIs do ePAG
**********************

As operações disponíveis estão descritas nos seguintes endereços abaixo:
____________________________________________________________________________
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
