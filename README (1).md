# Análise de Logística Empresarial — Power BI

## Sobre o projeto

Projeto de análise de dados voltado ao acompanhamento de pedidos, vendas, status de entrega e devoluções. A proposta é transformar registros operacionais em indicadores e visualizações que apoiem a leitura do desempenho comercial e ajudem a identificar pontos que merecem atenção na operação.

## Objetivos

- Acompanhar volume de pedidos, quantidades e valores registrados.
- Comparar resultados por canal de venda, categoria, produto, período e cidade.
- Monitorar a distribuição dos pedidos por status.
- Explorar o volume, os motivos e a situação das devoluções.
- Organizar os dados em um dashboard interativo para facilitar a análise.

## Ferramentas

- **Microsoft Excel:** base de dados e validações exploratórias.
- **Microsoft Power BI:** modelagem, indicadores, filtros e visualização dos resultados.

## Base de dados e modelo

A planilha contém seis abas: `Clientes`, `Produtos`, `Pedidos`, `Devolucoes`, `Validação Questões` e `Relacionamentos`. As tabelas principais registram 100 clientes, 100 produtos, 200 pedidos e 40 registros de devolução.

Relacionamentos documentados:

- `Clientes[ID_Cliente]` → `Pedidos[ID_Cliente]` (1:N)
- `Produtos[ID_Produto]` → `Pedidos[ID_Produto]` (1:N)
- `Pedidos[ID_Pedido]` → `Devolucoes[ID_Pedido]` (1:N)

## Etapas do trabalho

1. **Conhecimento da base:** identificação das tabelas, colunas, chaves e campos de análise.
2. **Verificação dos dados:** conferência de completude dos campos principais e análise da consistência entre IDs e tabelas relacionadas.
3. **Estruturação do modelo:** organização das relações entre clientes, produtos, pedidos e devoluções.
4. **Definição dos indicadores:** volume de pedidos, quantidade, valor líquido registrado, status e devoluções.
5. **Construção do dashboard:** cartões de indicadores, gráficos por mês, canal, categoria, produto, status e motivo de devolução, além de segmentadores para explorar os dados.
6. **Interpretação:** leitura dos resultados, registro de ressalvas e identificação de oportunidades para a próxima versão da análise.

## Principais números da base

| Indicador | Resultado | Como interpretar |
|---|---:|---|
| Pedidos registrados | 200 | Total de registros na tabela `Pedidos` |
| Quantidade nos pedidos | 346 | Soma da quantidade registrada em todos os status |
| Valor líquido registrado | R$ 220.919,30 | Soma de `Valor_Liquido` considerando todos os status |
| Valor líquido de pedidos entregues | R$ 148.997,56 | Soma de `Valor_Liquido` apenas para pedidos com status `Entregue` |
| Pedidos entregues | 137 | 68,5% do total de pedidos |
| Pedidos em transporte | 45 | 22,5% do total de pedidos |
| Pedidos cancelados | 18 | 9,0% do total de pedidos |
| Registros de devolução | 40 | Existem 40 IDs de pedido únicos na tabela de devoluções |
| Quantidade devolvida | 60 | Soma de `Quantidade_Devolvida` |

**Definição importante:** para esta documentação, a taxa de pedidos com devolução é calculada como 40 pedidos com registro de devolução ÷ 200 pedidos registrados = **20%**. Essa definição deve ficar explícita no dashboard. Ela é diferente da razão entre unidades devolvidas e unidades registradas nos pedidos.

## Principais descobertas

- **O Site é o principal canal em volume:** 99 pedidos, com R$ 116.859,74 em valor líquido registrado (52,9% da soma total).
- **Informática concentra o maior valor por categoria:** R$ 133.170,26, equivalente a aproximadamente 60,3% do valor líquido registrado.
- **Há pedidos que exigem acompanhamento operacional:** 45 aparecem como “Em transporte” e 18 como “Cancelado”. A base não inclui datas de entrega prevista e realizada, portanto não permite medir atraso ou cumprimento de SLA.
- **As devoluções estão distribuídas igualmente por motivo:** oito registros para cada uma das cinco categorias da base. Não há um motivo dominante nesta amostra.
- **Há itens de devolução ainda em análise:** 13 dos 40 registros estão com status `Em análise`.
- **Existe uma oportunidade de padronização textual:** alguns nomes de produtos na tabela `Pedidos` contêm espaços extras no início/fim. A padronização desses valores ajuda a evitar que um mesmo produto seja agrupado como mais de uma categoria de texto.

O período de pedidos encontrado na base vai de **01/01/2026 a 26/10/2026**. Outubro é um mês parcial no conjunto analisado.

## Habilidades demonstradas e desenvolvidas

- Exploração e leitura de bases tabulares.
- Identificação de entidades, chaves e relacionamentos 1:N.
- Conferência de integridade básica dos dados.
- Definição e interpretação de indicadores de negócio.
- Construção de dashboard com cartões, gráficos e segmentadores no Power BI.
- Análise comparativa por período, canal, categoria, produto, cidade e status.
- Comunicação de descobertas e ressalvas de forma orientada ao negócio.
- Identificação de oportunidades para melhoria da qualidade e da governança dos dados.

## Próximos passos recomendados

- Formalizar as regras dos KPIs, especialmente faturamento, itens vendidos e taxa de devolução.
- Padronizar nomes e categorias textuais antes da agregação.
- Investigar o motivo dos cancelamentos e o tempo de permanência em cada status.
- Acrescentar datas previstas e realizadas de entrega, prazo prometido, frete e custo logístico para permitir análises de SLA, eficiência operacional e rentabilidade.

## Arquivos do projeto

- `Dados_Logistica_Empresarial.xlsx` — base utilizada na análise.
- `Dashboard_Analise_Logistica_Concluido.pbix` — dashboard do Power BI.
- `Apresentacao_Projeto_Logistica.pptx` — apresentação do processo, indicadores, achados e recomendações.

---

*Projeto de portfólio — Análise de Dados aplicada à operação comercial e logística.*
