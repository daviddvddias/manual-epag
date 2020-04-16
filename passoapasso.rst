Passo a passo para utilizar a plataforma ePAG
*********************************************

Para integrar um serviço público com a plataforma ePAG é necessário executar alguns passos:


1. Cadastre seu serviço no SISGRU:
----------------------------------
Um requisito para integrar é ter seu serviço cadastrado na SISGRU.

**Como fazer:**
Solicite para o representante do órgão no SISGRU.....

É necessário cadastrar cada serviço na Aba `Pagtesouro` do SISGRU. 

.. figure:: _imagens/imagem_sisgru_servico.png
   :scale: 55 %
   :align: center
   
   Tela no SISGRU para cadastro de serviços
   

.. note::
   É necessário ter as credenciais no SISGRU. Caso não possua é necessário que formalizem por email para os coordenadores da STN/COFIN a solicitação de entrada no projeto Piloto do PagTesouro que faz integração com o Banco do Brasil para a modalidade de débito em conta.
   Os email são: fabiano.pereira AT tesouro.gov.br e roberta.pereira AT tesouro.gov.br


.. attention::
   **Cada token é único por UG.**


2. Chame a  API com os dados cadastrados
----------------------------------------
Seu sistema precisa utilizar os dados cadastrados no passo anterior durante a chamada a API.
Cada Beared Token é único por UG e deve ser solicitado a STN.

.. important::
   Esse código é específico para cada serviço. Não utilize códigos de outros serviços.
   O Bearer Token deve ser enviado pelo backend e não pode ser disponibilizado para o navegador do cidadão.


3. Exibir tabs ou janela modal
--------------------------------

Veja exemplo em:
https://v-epag.estaleiro.serpro.gov.br/simulador/#/pages/pagamento/modal

.. note::
  Adicionar HTML funcional e remover link acima.


4. Verifique se o pagamento foi realizado
-----------------------------------------

Para verificar se o pagamento foi realizado é necessário pesquisar tanto no SISGRU como no ePAG.

**Como fazer:**
Disponibilize um callback para o SISGRU para utilizar o débito online e verifique no SISGRU utilizando o webservice específico do SISGRU.
Acesse o `manual do Webservice do SISGRU`_ para verificar como utilizar.
O idPagamento retornado pelo ePag não pode ser utilizado no Webservice do SISGRU para verificação do status do pagamento do boleto.

.. important::
   O método de segurança do ePAG é diferente do método de segurança do SISGRU.
   Não são as mesmas credenciais usadas nessas duas operações. Para verificar os
   dois ambientes é necessário ter a permissão tanto no ePAG como no SISGRU.


.. _`manual do Webservice do SISGRU`: https://www.tesouro.fazenda.gov.br/sisgru
.. _`siga o procedimento para obter as credenciais`: https://www.example.com
