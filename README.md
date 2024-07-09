# Gerador de Dados Simulados e Validador de Arquivo CSV

Este projeto consiste em um conjunto de scripts Python para gerar dados simulados de eventos de produtos e validar a integridade desses dados em um arquivo CSV.

## Funcionalidades

### Script Gerador de Dados (`data_simulated_aws_sg.py`)

- Gera 1000 linhas de dados simulados para eventos de produtos.
- Cada linha contém:
  - ID_PRODUTO: Um número inteiro aleatório entre 1000 e 1024.
  - DATA_EVENTO: Uma data aleatória no intervalo entre 31 de dezembro de 2023 e 3 de julho de 2024.
  - PRECO: Um preço aleatório entre R$10,00 e R$200,00, arredondado para duas casas decimais.
  - FLAG_PROMOCAO: Um valor binário (0 ou 1) indicando se o produto estava em promoção no momento do evento.
  - QUANTIDADE_ESTOQUE: Um número inteiro aleatório entre 50 e 100, representando a quantidade de produtos em estoque no momento do evento.

### Script Validador de Arquivo (`test_python_data.py`)

- Verifica se o arquivo CSV gerado pelo `data_simulated_aws_sg.py` está correto.
- Realiza as seguintes validações:
  - Confirma se o cabeçalho do arquivo está correto.
  - Verifica se o número total de linhas no arquivo corresponde ao esperado (1001 linhas, incluindo o cabeçalho).
  - Checa os tipos de dados em cada coluna para garantir consistência.

## Requisitos

- Python 3.x instalado no sistema.

## Uso

### Geração dos Dados

1. Execute o script `data_simulated_aws_sg.py` para gerar automaticamente um arquivo CSV com dados simulados. Abra um terminal ou prompt de comando e digite:
   ```
   python data_simulated_aws_sg.py
   ```
2. O arquivo gerado será salvo como `dados_simulados.csv` no mesmo diretório.

### Validação do Arquivo Gerado

1. Execute o script `test_python_data.py` para verificar a integridade do arquivo CSV gerado. No terminal ou prompt de comando, digite:
   ```
   python test_python_data.py
   ```
2. O validador verificará se o arquivo `dados_simulados.csv` está correto conforme as especificações mencionadas.

## Estrutura do Arquivo CSV

O arquivo CSV gerado terá as seguintes colunas:

- ID_PRODUTO: Identificador único do produto.
- DATA_EVENTO: Data do evento de registro do dado no formato 'AAAA-MM-DD'.
- PRECO: Preço do produto no momento do evento.
- FLAG_PROMOCAO: Indicador se o produto estava em promoção (0 = não, 1 = sim).
- QUANTIDADE_ESTOQUE: Quantidade de produtos em estoque no momento do evento.
