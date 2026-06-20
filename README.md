# 📦 Brazilian E-Commerce Intelligence — Olist Dataset

> Relatório executivo de análise de e-commerce para investidores, construído com dados reais do marketplace Olist (2016–2018).

---

## 📌 Sobre o Projeto

Este projeto foi desenvolvido como parte do **Tech Challenge — Fase 1** do programa de pós-graduação **DTAT (Data Analytics) da POSTECH FIAP**.

O objetivo é transformar dados transacionais brutos em uma narrativa clara sobre desempenho comercial, eficiência logística e satisfação do cliente, com recomendações acionáveis para investidores.

---

## 📊 Dataset

**Brazilian E-Commerce Public Dataset by Olist**
- 🔗 Fonte: [Kaggle — olistbr/brazilian-ecommerce](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)
- ~100 mil pedidos reais entre **setembro de 2016** e **outubro de 2018**
- Dados anonimizados pela própria Olist
- 9 tabelas interconectadas

### Tabelas utilizadas

| Tabela | Descrição |
|---|---|
| `olist_orders_dataset` | Pedidos com datas e status |
| `olist_order_items_dataset` | Itens por pedido (preço, frete) |
| `olist_order_payments_dataset` | Pagamentos por pedido |
| `olist_order_reviews_dataset` | Avaliações dos clientes |
| `olist_customers_dataset` | Dados de clientes |
| `olist_products_dataset` | Catálogo de produtos |
| `olist_sellers_dataset` | Dados de vendedores |
| `olist_geolocation_dataset` | Coordenadas por CEP |
| `product_category_name_translation` | Tradução de categorias |

---

## 🔧 Arquitetura e ETL

Todo o processo de transformação foi realizado **dentro do Power BI**, utilizando o **Power Query (linguagem M)** como ferramenta de ETL — sem dependência de ferramentas externas.

### Transformações realizadas

- ✅ Integração das 9 tabelas em um **modelo estrela (Star Schema)**
- ✅ Tradução de categorias de produtos e meios de pagamento para português
- ✅ Cálculo de `lead_time_dias` (dias entre compra e entrega)
- ✅ Criação de `status_entrega` (No prazo / Atrasado / Não entregue)
- ✅ Agregação de pagamentos por pedido (merge de parcelas)
- ✅ Deduplicação de reviews (1 review por pedido)
- ✅ Correção de locale (`en-US`) para leitura correta de valores decimais
- ✅ Agregação de geolocalização por CEP (redução de 1M → ~19k linhas)

### Modelo de dados

```
fFatoPedidos (112.650 linhas — granularidade de item)
    ├── dClientes
    │     └── dGeolocalizacao
    ├── dProdutos (com tradução de categorias)
    ├── dVendedores
    └── dCalendario
```

---

## 📈 Principais Análises

### 💰 Crescimento e Receita
- GMV Total: **R$ 15,8 milhões** no período
- Ticket Médio: **R$ 161** por pedido
- **98.666 pedidos** realizados
- SP representa **37% do GMV** total

### 🚚 Logística e SLA
- **98% dos pedidos** entregues com sucesso
- Lead time médio: **~12 dias**
- Correlação negativa entre tempo de entrega e satisfação do cliente

### 💳 Pagamentos
- **75,9%** dos pagamentos via cartão de crédito
- **19,9%** via boleto
- Média de **3,7 parcelas** por pedido no cartão

### ⭐ Satisfação
- NPS aproximado: **63%**
- Review score médio: **4,07 / 5,0**
- Beleza & Saúde: categoria com melhor volume + satisfação

---

## 🗂️ Estrutura do Repositório

```
olist-ecommerce-analysis/
├── powerbi/
│   └── olist_dashboard.pbix       ← Dashboard Power BI completo
├── data/
│   └── README_dados.md            ← Instruções para baixar o dataset
└── README.md
```

> ⚠️ **Os CSVs do dataset não estão versionados** por questões de tamanho.
> Baixe diretamente do [Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) e coloque na pasta `data/raw/`.

---

## 🛠️ Tecnologias

| Ferramenta | Uso |
|---|---|
| **Power BI Desktop** | Dashboard, modelagem e visualizações |
| **Power Query (M)** | ETL — limpeza e transformação dos dados |
| **DAX** | Medidas calculadas e KPIs |
| **HTML Content (visual)** | Dashboard customizado em HTML/CSS/SVG |

---

## 🚀 Como reproduzir

1. Baixe o dataset no [Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)
2. Extraia os CSVs na pasta `C:\Users\SEU_USUARIO\Downloads\FIAP\db\`
3. Abra o arquivo `powerbi/olist_dashboard.pbix` no Power BI Desktop
4. Clique em **Atualizar** — as queries vão recarregar automaticamente

---

## 📋 Recomendações para Investidores

1. **Expansão regional** — Norte e Nordeste têm alta demanda reprimida mas lead times elevados. Investimento logístico nessas regiões tem alto potencial de ROI.

2. **Foco em categorias de alto valor** — Relógios, Informática e Automotivo têm ticket médio acima de R$ 180. Estratégias de curadoria e garantia podem aumentar GMV sem aumentar volume de pedidos.

3. **Retenção de clientes** — A maioria dos clientes realiza apenas uma compra no período. Programas de fidelização têm impacto direto na receita recorrente.

---

## 👤 Autor

**Gabriel Zacharias**
Analista de Dados Sênior · POSTECH FIAP DTAT

---

## 📄 Licença

Dataset: [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/) — Olist
Código e análise: MIT License
