# 📊 Monitoramento Estratégico: Transações Pix & Eficácia do MED
Painel analítico integrado ao Censo IBGE e dados abertos do Banco Central do Brasil.

Este repositório armazena os artefatos, consultas SQL e a estrutura de dados desenvolvidos no Databricks Lakeview para monitoramento executivo, análise regional e acompanhamento dinâmico das transações Pix e do Mecanismo Especial de Devolução (MED).

---

## 🛠️ Stack Tecnológica
* **Plataforma:** Databricks (AI/BI Lakeview Dashboards)
* **Engenharia de Dados:** Spark SQL, Arquitetura Medallion (Camada Gold)
* **Modelagem:** Dimensão Temporal Contínua (`Forward Fill` para janelas sem ocorrências)

---

## 📈 Estrutura do Dashboard

### 1. Visão Executiva & Tendência Histórica
*Acompanhamento dos principais indicadores de volume, liquidação e taxas de contestação.*
* **Cards:** Volume Total, Total de Transações, Ticket Médio Nacional, Taxa Efetiva MED.
* **Gráfico 1.1: Evolução Mensal do Volume Financeiro Pix (R$)**  
  *Transações mensais liquidadas no SPI. Variações expressivas no final do ano refletem pagamentos de 13º e consumo sazonal.*
* **Gráfico 1.2: Evolução Mensal do Ticket Médio Nacional (R$)**  
  *Média de Referência: ~R$ 460 | Faixa típica: R$ 420 a R$ 510*

---

### 📍 2. Panorama Regional & Demografia IBGE: Liquidez e Intensidade Per Capita
*Mapeamento dos fluxos líquidos entre macrorregiões brasileiras e correlação da densidade transacional do Pix com as estimativas populacionais do IBGE.*
* **Card:** Saldo Líquido Inter-Regional  
  *Visão Estrutural (Acumulado Histórico).*
* **Gráfico 2.1: Balança de Liquidez Inter-Regional (Entradas vs. Saídas)**  
  *Posição Mensal de liquidez líquida das macrorregiões brasileiras. Regiões receptoras (verde) recebem mais capital do que enviam; regiões emissoras (vermelho) apresentam saldo líquido negativo de capital.*
* **Gráfico 2.2: Balança Regional e Concentração de Volume Pix**  
  *Montante total transacionado (R$) e porcentagem de concentração regional do Pix (valores apresentados nas barras e no detalhe interativo).*

---

### 👥 3. Comportamento PF/PJ & Canais de Pagamento
*Dinâmica transacional (P2P, P2B, B2P, B2B) e maturidade digital por faixa etária.*
* **Cards:** 
  * Ticket Médio B2B *(Motor de Liquidez - PJ para PJ)*
  * Ticket Médio P2B *(Termômetro Varejo - PF para PJ)*
  * Ticket Médio P2P *(Base de Capilaridade - PF para PF)*

---

### 📍 4. Inteligência de Risco & Eficácia do MED
*Funil operacional de contestações, volume devolvido e causas de perda financeira.*
* **Gráfico 4.1: Funil de Resolução Operacional do MED (Consolidado)**  
  *Notificações de infração e pedidos de devolução (MED). O registro de contestação não implica necessariamente comprovação de fraude culposa.*
* **Gráfico 4.2: Causas de Falha na Devolução de Valores Fraudados (Consolidado)**  
  *Distribuição dos fatores que impedem o ressarcimento após deferimento da contestação.*
* **Gráfico 4.3: Evolução Mensal da Recuperação MED (%)**  
  *Percentual mensal de liquidação de devoluções sobre o total de fraudes confirmadas, destacando a eficácia das medidas de bloqueio cautelar e retenção de saldo.*

---

## ⚙️ Regras de Negócio e Tratamento de Dados

* **Preenchimento Contínuo (*Forward Fill*):** O painel utiliza uma malha de calendário dinâmico para garantir que meses sem novas ocorrências repliquem a última informação válida disponível.
* **Transparência de Competência (`Mês e Ano de Referência Original`):** Exibição explícita do mês de origem dos dados replicados.
* **Filtros Globais:** Sincronizados de ponta a ponta na camada de datasets para garantir consistência nos KPIs.

---
