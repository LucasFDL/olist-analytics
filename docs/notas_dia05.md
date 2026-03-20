# Notas Dia 05 — Olist Analytics

## O que aprendi

- Multi-join é encadear merges sequenciais — cada merge adiciona uma tabela
  nova usando a chave de ligação correta
- A base usada em cada análise importa: usar um DataFrame com mais merges
  pode excluir linhas sem correspondência nas tabelas adicionais, o que
  distorce resultados de análises que não dependem dessas tabelas
- Volume absoluto vs percentual muda completamente o ranking — SP lidera em
  atrasos absolutos mas tem a menor taxa proporcional do país
- Frete ratio por estado revela desigualdade logística clara: Norte e Nordeste
  pagam proporcionalmente muito mais caro do que o Sudeste
- Categorias de nicho tendem a ter ticket médio mais alto — quem compra PCs
  num marketplace paga mais do que quem compra flores

## O que foi feito no projeto

- Carregamento e inspeção de `sellers` — 4ª tabela integrada ao dataset
- Merge de `order_full_completed` com `sellers` pra montar `orders_final`,
  o DataFrame com as 4 tabelas unidas
- Análise de ticket médio por categoria de produto
- Análise de frete ratio por estado — cruzamento da coluna `freight_ratio`
  que estava criada mas nunca tinha sido usada assim
- Cálculo da taxa de atraso por estado em percentual, corrigindo a análise
  anterior que usava só volume absoluto
- Adição de todos os markdowns de observação nas seções novas do notebook

## Observações sobre os dados

- RO e RR chegam a quase 60% de frete ratio — o frete custa quase tanto
  quanto o produto nessas regiões
- AL tem 26,5% de taxa de atraso — mais de 1 em cada 4 pedidos chega tarde
- A hipótese levantada no dia 4 se confirmou: quem compra no Norte e Nordeste
  tende a escolher produtos mais caros, provavelmente pra compensar o frete
  alto
- Fica em aberto se o atraso no Nordeste é logístico ou se o prazo estimado
  já é irreal pra essas regiões

## Próximos passos

- Visualizações dos principais insights
- Pandas Puzzles 31-40 (pendente desde dia 4)
- Kaggle lições 5-6
