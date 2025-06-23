
# Coleta de Dados do Bitcoin com Python, SQLAlchemy e PostgreSQL

Este projeto realiza a extração periódica do valor do Bitcoin utilizando a API da Coinbase, trata os dados e armazena-os em um banco de dados PostgreSQL utilizando SQLAlchemy.

## Funcionalidades
- Extração do preço do Bitcoin em tempo real
- Tratamento e estruturação dos dados
- Armazenamento dos dados em banco PostgreSQL
- Execução automática em intervalos definidos

## Bibliotecas Utilizadas
- **requests**: Realiza requisições HTTP para consumir a API da Coinbase.
- **sqlalchemy**: ORM para manipulação do banco de dados PostgreSQL.
- **datetime**: Manipulação de datas e horários.
- **time (sleep)**: Pausa a execução entre as coletas.
- **dotenv**: Carrega variáveis de ambiente do arquivo `.env` (opcional, para segurança de credenciais).
- **os**: Manipulação de variáveis de ambiente do sistema.

![SQLAchemy](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d7/SQLAlchemy.svg/250px-SQLAlchemy.svg.png)
![Python](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Python-logo-notext.svg/150px-Python-logo-notext.svg.png)
![PostGreSQL](https://kinsta.com/wp-content/uploads/2022/02/postgres-logo.png)

## Estrutura do Código
- `extrair_dados_bitcoin()`: Faz a requisição à API da Coinbase e retorna o JSON com o valor do Bitcoin.
- `tratar_dados_bitcoin(dados_json)`: Recebe o JSON bruto, extrai os campos relevantes e adiciona um timestamp.
- `salvar_dados_sqlalchemy(dados)`: Salva os dados tratados no banco PostgreSQL usando SQLAlchemy.
- Loop principal: Executa a extração, tratamento e salvamento dos dados em intervalos definidos (atualmente 2 segundos).

## Como Executar
1. Instale as dependências:
   ```bash
   pip install requests sqlalchemy psycopg2-binary python-dotenv
   ```
2. Configure a string de conexão do banco de dados PostgreSQL na variável `DATABASE_URL`.
3. Execute o script:
   ```bash
   python exemplo_06.py
   ```

## Observações
- O script cria automaticamente a tabela `bitcoin_dados` caso não exista.
- O intervalo de coleta pode ser ajustado alterando o valor passado para `sleep()`.
- Certifique-se de que o banco de dados PostgreSQL está acessível e as credenciais estão corretas.

---





