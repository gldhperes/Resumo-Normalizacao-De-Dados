# Resumo Normalização De Dados.

É um processo que visa examinar os atributos de uma entidade (tabela) com o objetivo de preservar a integridade dos dados, estabilizar o modelo e eliminar redundancia de dados.

### Primeira Forma Normal (1FN)
O objetivo é retirar os atributos ou grupos repetitivos. Para as informações que se repetem em uma tabela, vinculadas a uma chave onde há apenas uma alteração do atributo, deve ser criada uma nova tabela relacionando a chave com a coluna que possui os atributos diferentes. Essa técnica é conhecida como *atomicidade de dados*. Exemplo:

![image](https://github.com/gldhperes/Resumo-Normalizacao-De-Dados/assets/111309686/669ab75a-7a20-4dfa-891d-f38c09db0647)

Perceba que o "autor" 1 possui 2 telefones diferentes. A fim de normalizar, a coluna "telefone" será removida e cria-se uma nova tabela relacionando o "codAutor" com os telefones. Segue o resultado abaixo:
![image](https://github.com/gldhperes/Resumo-Normalizacao-De-Dados/assets/111309686/6f249930-8365-4803-948b-b4256f208f79)
![image](https://github.com/gldhperes/Resumo-Normalizacao-De-Dados/assets/111309686/413669a2-61f6-40fe-97ca-315213ea0dcd)

### Segunda Forma Normal (2FN)
O objetivo é separar as dependências parciais. É preciso que as tabelas estejam na 1FN e que cada uma contenha dados sobre uma e somente uma entidade, onde as colunas que dependem parcialmente da PK.
Ou seja, quando os atributos não-chaves dependem parcialmente de chave concatenada. Por exemplo:
![image](https://github.com/gldhperes/Resumo-Normalizacao-De-Dados/assets/111309686/3e7d4273-2245-485b-818a-c50d91b98283)

Nesta tabela (Vendas), podemos ver que o "nomecliente" refere-se ao "codcliente", mas não tem total dependencia com a chave primaria na tabela (codvenda). Logo podemos criar uma outra tabela (Cliente) referenciado o "codcliente" com "nomecliente" e seus possiveis atributos. Então a divisão ficaria assim:

![image](https://github.com/gldhperes/Resumo-Normalizacao-De-Dados/assets/111309686/e71d4411-5d8a-4e82-baf0-7ab59c28c973)
![image](https://github.com/gldhperes/Resumo-Normalizacao-De-Dados/assets/111309686/1911ad20-ecf5-41b7-b8ba-eec120692da8)
