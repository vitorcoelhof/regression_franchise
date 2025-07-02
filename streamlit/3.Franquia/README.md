# Previsão de Custos para Abrir uma Franquia com Regressão Linear

Este projeto utiliza Python, Streamlit e scikit-learn para simular o valor do investimento inicial necessário para abrir uma franquia, com base em dados históricos e regressão linear.

## Descrição do Projeto
O arquivo `reg_lin.py` implementa uma aplicação web interativa que:
- Carrega um conjunto de dados (`slr12.csv`) contendo valores anuais de franquia e custos iniciais.
- Exibe os dados em uma tabela e em um gráfico de dispersão com a linha de regressão.
- Permite ao usuário inserir um novo valor anual de franquia e, ao clicar em "Processar", calcula e exibe a previsão do custo inicial para abertura da franquia usando um modelo de regressão linear.

## Como Executar
1. Instale as dependências necessárias:
   - `streamlit`
   - `pandas`
   - `scikit-learn`
   - `matplotlib`

2. Execute o comando abaixo no terminal:
   ```powershell
   streamlit run reg_lin.py
   ```

3. Acesse a aplicação pelo navegador, conforme instruções do Streamlit.

## Objetivo
O objetivo é demonstrar, de forma simples e visual, como a regressão linear pode ser utilizada para prever custos de investimento inicial em franquias a partir de dados históricos.

---

**Autor:** Seu Nome
