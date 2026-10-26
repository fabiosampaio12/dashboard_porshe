#Perguntas de negócio#
Escolhi três perguntas porque cada uma aponta para uma decisão comercial diferente, e a planilha já tinha modelo, cidade, estado, preço e pagamento para sustentá-las.

Pergunta	Por que
Quais famílias de modelo geram mais receita?	Priorizar estoque e campanha. Receita sozinha engana se um modelo vende pouco e é muito caro, então quantidade e preço médio entram junto.
Em quais estados a receita é mais forte?	Direcionar esforço comercial por região, sem misturar volume com ticket alto.
Como o pagamento se relaciona com o valor?	Ver método mais usado e se o ticket médio muda entre cartão, financiamento, transferência e outros.
Prompt até a versão final
Não houve um único prompt. O pedido foi evoluindo no chat:

Pedido inicial: dashboard em HTML, visual elegante, filtros de modelo, ano, cidade e método de pagamento, respondendo às três perguntas.
Limpeza: fazer a limpeza no próprio HTML, sem Excel. Preço ilegível vira inválido e sai só do cálculo financeiro. A venda permanece.
Opção C: indicadores com dados válidos e uma tabela separada de revisão.
Arquivo completo: HTML com os 100 registros sanitizados embutidos.
Ajuste de layout: tirar a tabela “Registros para revisão”, colocar título chamativo e um gráfico de receita por ano.
Correção: a versão seguinte zerou os números. Voltei ao HTML que calculava certo, sem a tabela de revisão, com o título novo.
O que mudou de fato no resultado: saiu a auditoria visual, entrou o título “Dashboard de Vendas”, e a regra de negócio ficou explícita — receita sem vendas Cancelled, datas INVALID sem data inventada.

Tratamento da base antes da dashboard
A planilha já vinha com colunas *Sanitized. O HTML final não relê o Excel. Ele usa esses campos já limpos, gravados no array rows.

O que a base exigia antes de confiar no número:

Preço: $79,500.00, 235000 USD, $121k e formatos mistos já estavam numéricos em SalesPriceSanitized.
Pagamento: wire, bank wire e wire-transfer já estavam agrupados em PayMethodSanitized.
Cidade e estado: capitalização e siglas já estavam em CitySanitized e StateSanitized.
Data: datas impossíveis (2024-02-30, April 31st) ficaram INVALID. Não foram corrigidas.
Na dashboard: canceladas saem da receita e do preço médio. Datas inválidas entram no filtro como “Data inválida”, não como um ano real. Modelos foram agrupados em família (911, 718, Cayenne, Macan, Taycan, Panamera) só na hora do gráfico.
Ferramenta usada
Chat no navegador, com o HTML escrito na conversa e aberto como arquivo local. Não usei Canvas (o recurso não estava disponível) e não usei Work nem um agente com skill. Foi um único fluxo de chat gerando o arquivo.

Endereço publicado
https://fabiosampaio12.github.io/dashboard_porshe/

