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

![image](https://github.com/gldhperes/Resumo-Normalizacao-De-Dados/assets/111309686/e2c492b1-85e1-467d-8cac-f606808b56bd)
![image](https://github.com/gldhperes/Resumo-Normalizacao-De-Dados/assets/111309686/633ffb4c-0f59-4821-bf56-eb4c5b57ea24)


### Terceira Forma Normal (3FN)
É uma tabela que, se e somente se, ela estiver na 2FN e todos os atributos não chave primária puderem ser obtidos somente através da chave primária. Por exemplo:

![image](https://github.com/gldhperes/Resumo-Normalizacao-De-Dados/assets/111309686/acd32fa9-4876-4e71-9316-981a3abe13df)

Note que o campo "transportadora" pode ser obtido tanto pelo atributo "codEditora" ou por "codTransp", porem pela definição cada atributo só deve ser obtido *única e exclusivamente* através da chave primária. Logo é criado uma nova tabela (Transportadoa) onde, por meio do atributo "codTransp" é possivel acessar a "transportadora". Resultado:

![image](https://github.com/gldhperes/Resumo-Normalizacao-De-Dados/assets/111309686/fa834634-7c06-4e99-a33c-035d57da037a)
![image](https://github.com/gldhperes/Resumo-Normalizacao-De-Dados/assets/111309686/d0239deb-257a-40fd-b4ac-85db4a958d2a)


