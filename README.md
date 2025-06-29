# WebScraping-MercadoLivre

Este projeto realiza uma pesquisa de mercado de notebooks no Mercado Livre utilizando web scraping, processamento de dados e visualização interativa.

## 1. Extração de Dados (Web Scraping)

- Utiliza o [Scrapy](https://scrapy.org/) para coletar informações de notebooks no Mercado Livre.
- O spider principal está em `src/extraction/coleta/spiders/notebook.py`.
- Os dados extraídos incluem: marca, nome, vendedor, avaliações, preços antigo e novo.

**Como rodar o spider:**
```sh
cd src/extraction
scrapy crawl notebook -o ../../data/data.jsonl
```

---

## 2. Transformação e Carga dos Dados

- O script `src/transformLoad/main.py` processa o arquivo `data.jsonl`:
  - Limpa e converte os dados (preços, avaliações, etc.).
  - Filtra produtos com preços entre R$1.000 e R$10.000.
  - Salva os dados tratados em um banco SQLite (`data/mercadolivre.db`), na tabela `notebook`.

**Como rodar a transformação:**
```sh
python src/transformLoad/main.py
```

---

## 3. Visualização dos Dados

- O dashboard interativo está em `src/dashboard/app.py` e utiliza [Streamlit](https://streamlit.io/).
- KPIs apresentados:
  - Total de notebooks coletados
  - Número de marcas únicas
  - Preço médio
  - Marcas mais frequentes
  - Preço médio por marca
  - Satisfação média por marca

**Como rodar o dashboard:**
```sh
streamlit run src/dashboard/app.py
```

---

## 4. Requisitos

Instale as dependências com:
```sh
pip install -r requirements.txt
```

---

## 5. Observações

- O projeto utiliza Python 3, Scrapy, Pandas e Streamlit.
- Os dados são salvos em `data/` para fácil acesso e versionamento.
- O spider está configurado para coletar até 10 páginas de resultados.

---

**Autor:** Vitor Ferreira

