# Dicionário de Dados

Este documento descreve as principais variáveis utilizadas no projeto Credit Risk Intelligence.

O dicionário de dados original completo é fornecido pela fonte do dataset. Este arquivo documenta as variáveis selecionadas para a análise.

## application_train.csv

| Coluna | Descrição | Uso de Negócio |
|---|---|---|
| `SK_ID_CURR` | Identificador único do cliente | Chave de junção entre as tabelas |
| `TARGET` | Indicador de dificuldade de pagamento | Target de inadimplência |
| `AMT_INCOME_TOTAL` | Renda anual do cliente | Segmentação de risco por renda |
| `AMT_CREDIT` | Valor de crédito solicitado | Análise de exposição de crédito |
| `AMT_ANNUITY` | Valor da parcela do empréstimo | Análise de comprometimento financeiro |
| `AMT_GOODS_PRICE` | Preço do bem financiado | Análise de contexto do empréstimo |
| `DAYS_BIRTH` | Idade do cliente em dias | Análise de perfil do cliente |
| `DAYS_EMPLOYED` | Tempo de emprego em dias | Análise de estabilidade profissional |
| `NAME_INCOME_TYPE` | Categoria de renda do cliente | Segmentação de risco |
| `NAME_EDUCATION_TYPE` | Nível de escolaridade do cliente | Análise de perfil descritivo |
| `NAME_FAMILY_STATUS` | Estado civil do cliente | Análise de perfil descritivo |
| `NAME_HOUSING_TYPE` | Tipo de moradia do cliente | Análise de perfil descritivo |
| `CNT_CHILDREN` | Número de filhos | Análise de perfil familiar |
| `CNT_FAM_MEMBERS` | Número de membros da família | Análise de perfil familiar |

## previous_application.csv

| Coluna | Descrição | Uso de Negócio |
|---|---|---|
| `SK_ID_PREV` | Identificador único da solicitação anterior | Identificação da solicitação anterior |
| `SK_ID_CURR` | Identificador único do cliente | Chave de junção com a tabela de clientes |
| `NAME_CONTRACT_STATUS` | Status da solicitação anterior | Análise de aprovação e recusa |
| `AMT_APPLICATION` | Valor solicitado na solicitação anterior | Análise de demanda de crédito |
| `AMT_CREDIT` | Valor concedido na solicitação anterior | Exposição histórica de crédito |
| `AMT_ANNUITY` | Parcela do empréstimo anterior | Análise de comprometimento de pagamento |
| `CNT_PAYMENT` | Número de parcelas | Análise de prazo do empréstimo |
| `DAYS_DECISION` | Dias antes da solicitação atual em que a decisão foi tomada | Análise de recência histórica |

## installments_payments.csv

| Coluna | Descrição | Uso de Negócio |
|---|---|---|
| `SK_ID_PREV` | Identificador do crédito anterior | Chave de junção com solicitações anteriores |
| `SK_ID_CURR` | Identificador único do cliente | Chave de junção com a tabela de clientes |
| `NUM_INSTALMENT_VERSION` | Versão do plano de parcelamento | Contexto do plano de pagamento |
| `NUM_INSTALMENT_NUMBER` | Número sequencial da parcela | Contexto do histórico de pagamento |
| `DAYS_INSTALMENT` | Data programada do pagamento, em dias | Referência de data de vencimento |
| `DAYS_ENTRY_PAYMENT` | Data real do pagamento, em dias | Referência de data de pagamento |
| `AMT_INSTALMENT` | Valor devido da parcela | Análise de valor devido |
| `AMT_PAYMENT` | Valor pago da parcela | Análise de comportamento de pagamento |

## Definições do Projeto

- `TARGET = 1`: Cliente com dificuldades de pagamento.
- `TARGET = 0`: Cliente sem dificuldades de pagamento.
- O dataset original utiliza variáveis anonimizadas e datas relativas.
- Variáveis derivadas e regras de transformação serão documentadas na camada Silver.
