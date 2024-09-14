# Documentação do Projeto: Sistema de Gerenciamento de Clientes para Universidade

## Descrição do Projeto

Este projeto visa criar um sistema de gerenciamento de clientes para uma universidade. A primeira fase do sistema inclui funcionalidades básicas para o cadastro de clientes, e operações de inserção, seleção e exclusão de registros. No futuro, o sistema será expandido para integrar outros setores da universidade, como administração acadêmica e financeira.

## Objetivo Final

O objetivo final do projeto é desenvolver um sistema robusto e escalável que possa ser utilizado para gerenciar informações de clientes, inicialmente focado em operações básicas de gerenciamento e com planos para futuras expansões.

## Estrutura da Tabela

### Criação da Tabela `tb_clientes`

```sql
CREATE TABLE tb_clientes (
    idClientes INT,
    Nome VARCHAR(50),
    CPF VARCHAR(50),
    RG VARCHAR(50),
    Data_Nascimento DATE,
    Sexo VARCHAR(1),
    Profissão VARCHAR(50),
    Nacionalidade VARCHAR(50),
    Logradouro VARCHAR(50),
    Número INT,
    Complemento VARCHAR(30),
    Bairro VARCHAR(30),
    Município VARCHAR(30),
    UF VARCHAR(2)
);
```

### Inserção de Dados

```sql
INSERT INTO tb_clientes (idClientes, Nome, CPF, RG, Data_Nascimento, Sexo, Profissão, Nacionalidade, Logradouro, Número, Complemento, Bairro, Município, UF)
VALUES
('1', 'Manoel', '88828383821', '32323', '2001-10-10', 'M', 'Estudante', 'Brasileira', 'Rua Joaquin Nabuco', '23', 'Casa', 'Cidade Nova', 'Porto União', 'SC'),
-- (mais registros seguem)
('15', 'Jessica', '', '', NULL, 'F', 'Estudante', '', '', NULL, '', '', 'União da Vitória', 'PR');
```

## Consultas Realizadas

1. **Ordenar por Nome em Ordem Decrescente**

   ```sql
   SELECT Nome, Sexo, Profissão
   FROM tb_clientes
   ORDER BY Nome DESC;
   ```

2. **Buscar Nomes com 'R'**

   ```sql
   SELECT Nome, Sexo, Profissão
   FROM tb_clientes
   WHERE Nome LIKE '%R%';
   ```

3. **Buscar Nomes com 'c'**

   ```sql
   SELECT Nome, Sexo, Profissão
   FROM tb_clientes
   WHERE Nome LIKE '%c%';
   ```

4. **Buscar Clientes com Bairro 'Centro'**

   ```sql
   SELECT Nome, Sexo, Profissão
   FROM tb_clientes
   WHERE Bairro = 'Centro';
   ```

5. **Buscar Clientes com Complemento Contendo 'A'**

   ```sql
   SELECT Nome, Sexo, Profissão
   FROM tb_clientes
   WHERE Complemento LIKE '%A%';
   ```

6. **Buscar Clientes do Sexo Feminino**

   ```sql
   SELECT Nome, Sexo, Profissão
   FROM tb_clientes
   WHERE Sexo = 'F';
   ```

7. **Buscar Clientes com CPF em Branco**

   ```sql
   SELECT Nome, Sexo, Profissão
   FROM tb_clientes
   WHERE CPF = '';
   ```

8. **Ordenar por Profissão em Ordem Crescente**

   ```sql
   SELECT Nome, Sexo, Profissão
   FROM tb_clientes
   ORDER BY Profissão ASC;
   ```

9. **Buscar Clientes com Nacionalidade Brasileira**

   ```sql
   SELECT Nome, Sexo, Profissão
   FROM tb_clientes
   WHERE Nacionalidade LIKE '%Brasileira%';
   ```

10. **Buscar Clientes com Número Não Nulo**

    ```sql
    SELECT Nome, Sexo, Profissão
    FROM tb_clientes
    WHERE Número IS NOT NULL;
    ```

11. **Buscar Clientes com UF 'SC'**

    ```sql
    SELECT Nome, Sexo, Profissão
    FROM tb_clientes
    WHERE UF = 'SC';
    ```

12. **Buscar Clientes com Data de Nascimento entre 2000-01-01 e 2002-01-01**

    ```sql
    SELECT Nome, Sexo, Profissão
    FROM tb_clientes
    WHERE Data_Nascimento BETWEEN '2000-01-01' AND '2002-01-01';
    ```

13. **Criar Endereço Completo**

    ```sql
    SELECT Nome, CONCAT(Logradouro, ', ', Número, ', ', IFNULL(Complemento, ''), ', ', Bairro, ', ', Município, ', ', UF) AS EnderecoCompleto
    FROM tb_clientes;
    ```

## Operações de Atualização e Exclusão

1. **Atualizar Dados do Cliente**

   ```sql
   UPDATE tb_clientes
   SET CPF = '45390569432',
       Sexo = 'M',
       Nacionalidade = 'Brasileira',
       UF = 'SC'
   WHERE idClientes = 16;
   ```

2. **Atualizar Data de Nascimento e Sexo**

   ```sql
   UPDATE tb_clientes
   SET Data_Nascimento = '1974-04-01',
       Sexo = 'M'
   WHERE idClientes = 17;
   ```

3. **Atualizar Profissão e Número**

   ```sql
   UPDATE tb_clientes
   SET Sexo = 'F',
       Profissão = 'Professora',
       Número = 123
   WHERE idClientes = 18;
   ```

4. **Excluir Cliente**

   ```sql
   DELETE FROM tb_clientes
   WHERE idClientes = 16;
   ```

5. **Excluir Cliente com Nome 'Sandra'**

   ```sql
   DELETE FROM tb_clientes
   WHERE Nome = 'Sandra';
   ```

## Futuras Expansões

A expansão do sistema para outros setores da universidade incluirá:
- Integração com módulos acadêmicos, financeiros e administrativos.
- Funcionalidades adicionais como relatórios, gerenciamento de cursos e integração com sistemas externos.
- Melhorias na interface e usabilidade.

## Contextualização para GitHub

### Projeto: **Sistema de Gerenciamento de Clientes para Universidade**

**Descrição:**  
Este projeto estabelece a base para um sistema de gerenciamento de clientes voltado para uma universidade. O sistema permite o cadastro de clientes e operações básicas de gerenciamento, com planos para futuras expansões para outros setores acadêmicos e administrativos.

**Tecnologias Utilizadas:**  
- SQL

**Estrutura do Projeto:**
- Criação e manipulação de tabelas
- Inserção, seleção e exclusão de dados
- Atualização de registros
- Planejamento para futuras expansões

**Objetivo:**  
Desenvolver um sistema de gerenciamento de clientes que será expandido para outras áreas da universidade, demonstrando habilidades na gestão de bancos de dados relacionais e planejamento de sistemas.

**Como Executar:**
1. Crie a tabela `tb_clientes` no banco de dados.
2. Insira os dados fornecidos.
3. Execute as consultas para verificar a integridade dos dados.
4. Realize atualizações e exclusões conforme necessário.

**Notas:**
- Ajuste as configurações do banco de dados, como `SQL_SAFE_UPDATES`, conforme necessário para executar as operações de atualização e exclusão.
