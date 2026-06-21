# Tech Challenge — Fase 1 | Data Analytics (POSTECH)
## Case E-commerce Olist — Relatório Executivo para Investidores

Relatório técnico-analítico que transforma os dados transacionais da **Olist** (marketplace brasileiro) em uma narrativa executiva sobre **crescimento e receita, eficiência logística, comportamento de pagamento e satisfação do cliente** — com recomendações acionáveis e uma previsão de receita de curto prazo.

> 📓 Análise completa: [`notebook/Tech_Challenge_Olist_Fase1.ipynb`](notebook/Tech_Challenge_Olist_Fase1.ipynb)
> 🎥 Vídeo executivo (até 5 min): _[link a preencher]_
> 📊 Apresentação executiva (storytelling): _[link a preencher]_

---

## 1. Sobre o projeto

Este repositório contém o código e a análise do **Tech Challenge da Fase 1** da pós-graduação em Data Analytics (POSTECH), baseado no [Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) (Kaggle). O objetivo foi construir um relatório executivo, com storytelling de dados, voltado a investidores e acionistas do setor de e-commerce.

O notebook segue cinco trilhas analíticas sugeridas no enunciado do desafio:

1. **Crescimento e Receita** — evolução mensal, ticket médio, participação por categoria/região, top sellers e produtos.
2. **Logística e SLA** — lead time da jornada do pedido, correlação entre atraso e satisfação, mapa de calor regional.
3. **Comportamento e Pagamentos** — formas de pagamento, parcelamento, segmentação RFM, taxa de recompra.
4. **Satisfação do Cliente** — distribuição de notas, drivers de insatisfação, temas recorrentes em avaliações negativas.
5. **Oportunidades, Previsão e Recomendações** — projeção de receita (3 meses), scorecard de vendedores, oportunidades de frete e síntese de recomendações.

## 2. Estrutura do repositório

```
.
├── data/                    # CSVs originais do dataset Olist (ver seção 4 — não versionados no Git)
├── charts/                  # Gráficos exportados em alta resolução (.png), prontos para a apresentação
├── notebook/
│   └── Tech_Challenge_Olist_Fase1.ipynb   # Notebook executivo completo (análise + insights)
├── requirements.txt         # Dependências Python
├── .gitignore
└── README.md
```

## 3. Como reproduzir a análise

```bash
# 1. Clone o repositório
git clone <url-deste-repositorio>
cd <pasta-do-repositorio>

# 2. Crie um ambiente virtual (opcional, recomendado)
python -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate

# 3. Instale as dependências
pip install -r requirements.txt

# 4. Baixe o dataset (ver seção 4) e coloque os 9 arquivos .csv na pasta data/

# 5. Execute o notebook
jupyter notebook notebook/Tech_Challenge_Olist_Fase1.ipynb
# (Run All / Executar Tudo)
```

Os gráficos são salvos automaticamente em `charts/` a cada execução, em alta resolução — prontos para serem usados diretamente nos slides da apresentação executiva.

## 4. Sobre os dados

O dataset **não é versionado neste repositório** (boa prática de governança de dados — evita repositórios pesados e dados duplicados). Para reproduzir a análise, baixe os arquivos diretamente no Kaggle:

🔗 **[Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)**

Arquivos esperados em `data/`:

| Arquivo | Conteúdo |
|---|---|
| `olist_customers_dataset.csv` | Clientes (id, CEP, cidade, UF) |
| `olist_orders_dataset.csv` | Pedidos (status, timestamps de compra/aprovação/entrega) |
| `olist_order_items_dataset.csv` | Itens do pedido (produto, vendedor, preço, frete) |
| `olist_order_payments_dataset.csv` | Pagamentos (tipo, parcelas, valor) |
| `olist_order_reviews_dataset.csv` | Avaliações (nota, comentários) |
| `olist_products_dataset.csv` | Produtos (categoria, peso, dimensões) |
| `olist_sellers_dataset.csv` | Vendedores (CEP, cidade, UF) |
| `olist_geolocation_dataset.csv` | CEP → latitude/longitude (não utilizado diretamente no notebook) |
| `product_category_name_translation.csv` | Tradução de categorias (PT → EN) |

## 5. Principais achados (resumo)

| Indicador | Valor |
|---|---:|
| GMV (volume transacionado) | R$ 13,2 milhões |
| Ticket médio (AOV) | R$ 159,80 |
| Taxa de recompra | ~3% |
| Nota média de avaliação | 4,09 / 5 |
| Tempo médio de entrega | 12,6 dias |
| Concentração geográfica (SP+RJ+MG) | ~66% da receita |

O detalhamento completo de metodologia, evidências e recomendações está no notebook e na apresentação executiva.

## 6. Governança e qualidade dos dados

As decisões de tratamento de dados (filtro de status de pedido, janela temporal de tendência, tratamento de nulos, granularidade das tabelas analíticas) estão integralmente documentadas na **Seção 5 (Governança e Qualidade dos Dados)** e no **Anexo (Seção 14)** do notebook, garantindo reprodutibilidade e transparência metodológica.

## 7. Autoria

**Grupo:** _[preencher com o nome do grupo / integrantes]_
**Disciplina:** Data Analytics — POSTECH | Tech Challenge — Fase 1
