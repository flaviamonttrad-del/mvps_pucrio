## Visão Geral do Projeto

Este projeto consiste num trabalho prático de **Engenharia e Análise de Dados** sobre o uso do **Pix** no Brasil e o funcionamento do **Mecanismo Especial de Devolução (MED)**, utilizado no combate a fraudes.

A solução foi desenvolvida na plataforma **Databricks**, organizada em três camadas de tratamento de dados (Bronze, Silver e Gold) e reúne informações públicas de fontes oficiais:
* **Transações Pix:** Volume de transferências e valores movimentados divulgados pelo Banco Central do Brasil (Bacen);
* **Notificações de Fraude (MED):** Pedidos de contestação, aprovações e valores devolvidos às vítimas pelo Bacen; e
* **Dados Demográficos do IBGE:** População das cidades e estados para calcular indicadores por habitante.

---

### Objetivos do Trabalho

O objetivo principal é construir um fluxo completo de dados para responder a perguntas práticas do dia a dia do Pix:

1. **Crescimento e Fraudes:** Medir o crescimento mensal do Pix (número de transações, montante total e valor médio);
2. **Diferenças Regionais:** Identificar quais regiões movimentam mais dinheiro, qual o gasto médio por pessoa e que áreas mais enviam ou recebem recursos;
3. **Perfil de Uso:** Compreender as transferências entre pessoas e empresas (P2P, P2B, B2B) e os meios de pagamento preferidos (chave Pix, QR Code ou dados manuais da conta) de acordo com a faixa etária;
4. **Devolução do Dinheiro (MED):** Descobrir a porcentagem de pedidos de devolução aceitos, o valor efetivamente recuperado e o motivo pelo qual o dinheiro não é devolvido (como a conta recebedora estar sem saldo);
5. **Boas Práticas de Dados:** Aplicar técnicas de engenharia de dados em nuvem, garantindo limpeza, organização, padronização visual para o formato brasileiro e atualização automatizada.
