# Utilizando Prompts para Gerar Insights de Relatórios de Vendas

## 📒 Descrição


## 🤖 Tecnologias Utilizadas
- [Chat DeepSeek](https://chat.deepseek.com/) 

## 🧐 Processo de Criação
---

### **1. Análise dos Dados de Vendas**
- **Objetivo**: Criar uma tabela de resumo de vendas por país, incluindo valores convertidos em Reais (BRL).
- **Dados de Entrada**: Três arquivos CSV com dados de vendas do produto Meganium em diferentes plataformas (AliExpress, Etsy e Shopee).
- **Estrutura dos Dados**:
  - Cada arquivo CSV continha informações como SKU, produto vendido, data, quantidade, preço unitário, preço total, moeda, país de entrega, cupom de desconto, valor do desconto, nome do comprador e data de nascimento.

---

### **2. Processamento dos Dados**
- **Agrupamento por País**:
  - Os dados foram organizados por país de entrega (`delivery_country`).
  - Para cada país, foram somadas as quantidades vendidas e os valores totais das vendas.
- **Conversão de Moedas**:
  - Os valores totais das vendas estavam em diferentes moedas (GBP, USD, EUR).
  - Para padronizar, converti todos os valores para Reais (BRL) usando taxas de câmbio aproximadas:
    - 1 GBP = 6,40 BRL
    - 1 USD = 5,20 BRL
    - 1 EUR = 5,60 BRL
  - A data do câmbio foi fixada como 30 de outubro de 2023.

---

### **3. Criação da Tabela de Resumo**
- **Colunas da Tabela**:
  - **País**: País de entrega.
  - **Data**: Data da venda.
  - **Produto Vendido**: Nome do produto vendido.
  - **Quantidade**: Quantidade vendida.
  - **Valor Total (Moeda Original)**: Valor total da venda na moeda original.
  - **Moeda**: Moeda original da venda (GBP, USD, EUR).
  - **Taxa de Câmbio (BRL)**: Taxa de câmbio usada para converter para BRL.
  - **Data do Câmbio**: Data da conversão (30/10/2023).
  - **Valor Total (BRL)**: Valor total da venda convertido para BRL.
- **Exemplo de Linha**:
  ```
  Austrália,2024-09-03,NEW MEGANIUM RG35XX,2,180 GBP,GBP,6.40,30/10/2023,1152.00
  ```

---

### **4. Geração do Arquivo CSV**
- **Formatação do CSV**:
  - O arquivo CSV foi formatado com vírgulas (`,`) como delimitadores.
  - Para garantir que os acentos e caracteres especiais fossem exibidos corretamente no Excel, foi adicionado o **BOM (Byte Order Mark)** no início do arquivo.
- **Conteúdo do CSV**:
  - O arquivo CSV contém todas as linhas da tabela de resumo, com os valores convertidos e formatados.

---

### **5. Solução para Problemas de Codificação no Excel**
- **Problema**: Ao abrir o CSV no Excel, os acentos e caracteres especiais apareciam incorretamente (ex: `PaÃ­s`).
- **Solução**:
  - Usei o **Notepad++** para salvar o arquivo CSV com codificação **UTF-8 com BOM**.
  - Isso garante que o Excel interprete corretamente a codificação UTF-8 ao abrir o arquivo.

---

### **6. Resumo do Processo**
1. **Coleta e Análise dos Dados**: Extraí os dados de vendas dos arquivos CSV.
2. **Agrupamento e Conversão**: Agrupei os dados por país e converti os valores para BRL.
3. **Criação da Tabela**: Estruturei a tabela com as colunas necessárias.
4. **Geração do CSV**: Salvei a tabela em um arquivo CSV, garantindo a codificação correta.
5. **Correção de Codificação**: Usei o Notepad++ para adicionar o BOM e garantir que o Excel exibisse os acentos corretamente.

---

### **Arquivo CSV Final**
O arquivo CSV gerado contém todas as informações de vendas por país, com valores convertidos para BRL e formatados para ser aberto corretamente no Excel.

## Características

- A empresa foca apenas em fabricação de consoles, deixando a distribuição e venda para terceiros
- Os produtos são vendidos globalmente


## Objetivos

- [ ]  Consolidar todas as bases de terceiros para realizar uma análise
- [ ]  Transformar dados de vendas e transformar em informações relevantes para o fabricante
- [ ]  Quais são os produtos mais populares em cada país
- [ ]  Como otimizar o processo de transporte e logistica até o momento da venda