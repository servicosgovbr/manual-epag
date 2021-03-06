﻿Apresentação
============

PagTesouro
**********

O PagTesouro é o serviço em construção do governo federal para disponibilizar 
meios de pagamentos de boleto, débito online e cartão de crédito para pagamentos. Essa documentação é baseada na versão 1.7 da documentação do PagTesouro (https://valpagtesouro.tesouro.gov.br/simulador/#/pages/api)

.. important::
    A STN ainda não informou se será necessário um credenciamento por partes dos *órgãos públicos*. O que há no momento é o credenciamento de Prestadores de Serviços de Pagamento.

Não há limitação nem de valor de pagamento e nem de quantidade de solicitações de pagamento ao utilizar o PagTesouro.

Formas de uso
*************

É possível usar de duas formas:

* Débito online
* Boleto bancário

O boleto bancário é somente para a GRU SIMPLES. Não há possibilidade de GRU Cobrança.
Não consta no boleto a data limite de pagamento. Pode haver pagamento após a data final de pagamento.

.. important::
    Os meios de débito online e boleto estão prontos na **primeira versão** do sistema e será desenvolvido em versão futura o cartão de crédito, débito e pagamento instantâneo.

Há uma expectativa de ter novas formas de uso com o chamamento das instituições financeiras. https://sisweb.tesouro.gov.br/apex/f?p=2501:9::::9:P9_ID_PUBLICACAO_ANEXO:8029

Pode haver cobrança de taxa pelas instituições financeiras. Essa taxa será pago pelo cidadão conforme item 5.1 do edital do chamamento.

O Banco Central divulgou o PIX em uma coletiva de imprensa.
https://www.youtube.com/watch?v=Fqr2eGhdqx8

Fluxo do débito online do Banco do Brasil
*****************************************

É necessário que o sistema cliente solicite o pagamento e que verifique se o pagamento foi de fato realizado.

.. important::
    Outras instituições financeiras devem estar habilitadas a partir de setembro - outubro de 2020.

Solicitação de pagamento
------------------------

.. image:: _imagens/fluxo_debito.png
   :scale: 75 %
   :align: center
   :alt: Fluxo simplificado da solicitação para débito online.

.. attention::
   O atributo proxima_url expira em 60 minutos e não pode ser utilizado nos status (CONCLUIDO, REJEITADO, CANCELADO).

Verificação de pagamento
------------------------

.. image:: _imagens/fluxo_verificacao_debito.png
   :scale: 75 %
   :align: center
   :alt: Fluxo simplificado de verificação de pagamento para débito online.
   
O processo de verificação do status do pagamento inicia ou por tempo ou por evento.

Fluxo do boleto bancário
************************

Solicitação de pagamento
------------------------

.. image:: _imagens/fluxo_boleto.png
   :scale: 100 %
   :align: center
   :alt: Fluxo simplificado do solicitação para boleto bancário.

.. attention::
   O PagTesouro só solicita a criação do boleto bancário. O **idPagamento** não é associado ao pagamento do boleto.
   É necessário o órgão verificar o pagamento.
   
.. attention::
   O atributo proxima_url expira em 60 minutos e não pode ser utilizado nos status (CONCLUIDO, REJEITADO, CANCELADO).

Fluxo do cartão de crédito
**************************

Não há possibilidade de cartão de crédito nessa versão do PagTesouro.

Fluxo do cartão de débito
*************************

Não há possibilidade de cartão de débito nessa versão do PagTesouro.

Fluxo de pagamento instantâneo
******************************

Não há possibilidade de pagamento instantâneo nessa versão do PagTesouro.

Exemplo de Integração 
*************************

Ferramenta de Automação Federal (LECOM) e PagTesouro - DÉBITO ONLINE
------------------------

.. image:: _imagens/fluxo_geral.png
   :scale: 50 %
   :align: center
   :alt: Fluxo geral do pagamento.

O processo de verificação do status do pagamento acontece de duas formas: por tempo ou por evento. 

.. important::
    A solicitação de criação do pagamento é feita pelo backoffice da ferramenta de automação, então os parâmetros (token, valor, serviço e etc) devem estar configurados nesse backoffice.


Ferramenta de Automação Federal (LECOM) e PagTesouro - BOLETO
------------------------

.. image:: _imagens/fluxo_geral_boleto.png
   :scale: 50 %
   :align: center
   :alt: Fluxo geral do pagamento.

O processo de verificação do status do pagamento do boleto é feito a parte pelo órgão.

.. important::
    A solicitação de criação do pagamento é feita pelo backoffice da ferramenta de automação, então os parâmetros (token, valor, serviço e etc) devem estar configurados nesse backoffice.

Estorno dos pagamentos
**********************

Se o contribuinte entender que o pagamento não deveria ter sido feito, 
deverá proceder como hoje na arrecadação de GRU via boleto, ou seja, 
pleitear a restituição junto ao órgão arrecadador e, caso o órgão entenda 
que deve ser feita, a restituição será feita também como hoje por meio de 
geração de OB em favor do contribuinte. Esta orientação consta na Instrução 
Normativa STN nº 02, de 22/05/2009 que regula o processo de arrecadação de GRU.


Informar ao cidadão sobre o pagamento
*************************************

Pode informar por e-mail ou por SMS.

Caso seja desejado pode-se entrar em contato com o Ministério da Economia para
utilizar a plataforma de SMS para envio de mensagem ao cidadão e informá-lo
sobre a situação do pagamento.
