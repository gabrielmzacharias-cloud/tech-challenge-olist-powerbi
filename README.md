# Tech Challenge - Fase 1 | E-commerce Olist

Projeto desenvolvido para o Tech Challenge da Pós Tech, com foco na construção de um relatório executivo para investidores e acionistas do setor de e-commerce, utilizando o **Brazilian E-Commerce Public Dataset by Olist**.

> Status do projeto: em finalização  
> Ferramenta principal: Power BI  
> Entregável principal: Dashboard executivo + storytelling + documentação de dados

---

## 1. Objetivo do projeto

Transformar dados transacionais de e-commerce em uma análise executiva clara, com foco em:

- desempenho comercial;
- eficiência logística;
- satisfação do cliente;
- oportunidades de crescimento;
- recomendações acionáveis para tomada de decisão.

A proposta do relatório é apoiar uma visão de negócio voltada a investidores, destacando onde a operação apresenta maior potencial de receita, risco operacional e oportunidade de melhoria.

---

## 2. Links do projeto

Preencha antes da entrega final:

| Item | Link |
|---|---|
| Repositório GitHub | `COLE_AQUI_O_LINK_DO_GITHUB` |
| Dashboard / PBIX | `COLE_AQUI_O_LINK_DO_ARQUIVO_OU_POWER_BI_SERVICE` |
| Apresentação executiva | `COLE_AQUI_O_LINK_DA_APRESENTACAO` |
| Vídeo executivo | `COLE_AQUI_O_LINK_DO_VIDEO` |

---

## 3. Base de dados

Fonte: Brazilian E-Commerce Public Dataset by Olist.

O dataset contém pedidos realizados entre 2016 e 2018 e possui tabelas relacionadas a clientes, pedidos, itens, produtos, vendedores, pagamentos, avaliações e geolocalização.

### Principais tabelas utilizadas

| Tabela | Finalidade |
|---|---|
| `olist_customers_dataset` | Dados de clientes e localização |
| `olist_orders_dataset` | Pedidos, status e datas da jornada |
| `olist_order_items_dataset` | Produtos vendidos, sellers, preço e frete |
| `olist_order_payments_dataset` | Formas de pagamento e parcelas |
| `olist_order_reviews_dataset` | Avaliações e satisfação dos clientes |
| `olist_products_dataset` | Dados dos produtos |
| `olist_sellers_dataset` | Dados dos vendedores |
| `olist_geolocation_dataset` | Coordenadas e localização por CEP |
| `product_category_name_translation` | Tradução das categorias |

---

## 4. Perguntas de negócio

O dashboard foi estruturado para responder perguntas como:

1. Como evoluíram os pedidos, a receita e o ticket médio ao longo do tempo?
2. Quais categorias, estados e sellers concentram maior desempenho comercial?
3. Como o prazo de entrega impacta a satisfação dos clientes?
4. Quais regiões apresentam maior risco logístico?
5. Quais oportunidades podem aumentar receita, reduzir atrasos ou melhorar a experiência do cliente?

---

## 5. Estrutura do repositório

```text
.
├── README.md
├── .gitignore
├── .gitattributes
├── docs/
│   ├── checklist_entrega.md
│   ├── como_subir_github.md
│   ├── dicionario_dados.md
│   ├── extrair_codigo_powerbi.md
│   ├── governanca_qualidade.md
│   ├── roteiro_video_5min.md
│   └── storytelling_executivo.md
├── src/
│   ├── dax/
│   │   └── medidas_base_olist.dax
│   ├── powerquery/
│   │   ├── README.md
│   │   └── exemplo_importacao_csv_olist.m
│   └── python/
│       └── validacao_qualidade_dados.py
├── reports/
│   └── coloque_aqui_o_pbix_ou_pbip.txt
├── presentation/
│   └── coloque_aqui_o_link_ou_arquivo_da_apresentacao.txt
├── data/
│   ├── raw/
│   │   └── README.md
│   └── processed/
│       └── README.md
└── assets/
    └── img/
        └── README.md
```

---

## 6. Como reproduzir o projeto

1. Baixar o dataset original.
2. Colocar os arquivos `.csv` na pasta `data/raw`.
3. Abrir o arquivo `.pbix` ou `.pbip` na pasta `reports`.
4. Ajustar o caminho dos arquivos no Power Query, se necessário.
5. Atualizar o modelo no Power BI.
6. Conferir as medidas DAX em `src/dax/medidas_base_olist.dax`.
7. Validar os principais indicadores com os checks de qualidade.

---

## 7. Principais indicadores

| Indicador | Descrição |
|---|---|
| Receita | Soma dos valores de produtos vendidos |
| Frete | Soma do valor de frete |
| Pedidos | Quantidade distinta de pedidos |
| Clientes | Quantidade distinta de clientes únicos |
| Ticket médio | Receita dividida pela quantidade de pedidos |
| Prazo médio de entrega | Diferença entre data de compra e data de entrega |
| % de atraso | Proporção de pedidos entregues após a data estimada |
| Review médio | Média da nota de avaliação do cliente |
| Receita por categoria | Receita agrupada por categoria de produto |
| Receita por UF | Receita agrupada por estado do cliente ou seller |

---

## 8. Recomendações executivas

As recomendações finais devem ser ajustadas conforme os resultados do seu PBIX. Uma estrutura sugerida:

1. **Priorizar categorias de alta receita e bom nível de satisfação**  
   Direcionar investimento para categorias com maior retorno e menor risco de experiência negativa.

2. **Atuar nas regiões com maior atraso logístico**  
   Reduzir gargalos de entrega pode melhorar reviews e recompra.

3. **Fortalecer sellers com alto desempenho**  
   Sellers com alto volume, baixo atraso e boas avaliações devem receber prioridade em campanhas, exposição e relacionamento.

4. **Monitorar categorias com alto frete ou baixo review**  
   Esses grupos podem prejudicar margem e percepção do cliente.

---

## 9. Observações

- Os dados são públicos e anonimizados.
- Os arquivos brutos não precisam ser versionados se forem muito pesados.
- O arquivo `.pbix` pode ser mantido no repositório usando Git LFS, caso ultrapasse o limite recomendado para arquivos grandes.
- Para melhor versionamento, prefira salvar também em formato Power BI Project (`.pbip`), quando disponível.

---

## 10. Autores

Preencha com os integrantes do grupo:

- Nome 1
- Nome 2
- Nome 3
