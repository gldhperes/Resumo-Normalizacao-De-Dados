# Resumo Normalização De Dados.

É um processo que visa examinar os atributos de uma entidade (tabela) com o objetivo de preservar a integridade dos dados, estabilizar o modelo e eliminar redundancia de dados.

### Primeira Forma Normal (1FN)
O objetivo é retirar os atributos ou grupos repetitivos. Para as informações que se repetem em uma tabela, vinculadas a uma chave onde há apenas uma alteração do atributo, deve ser criada uma nova tabela relacionando a chave com a coluna que possui os atributos diferentes. Essa técnica é conhecida como *atomicidade de dados*. Exemplo:

![image](https://github.com/gldhperes/Resumo-Normalizacao-De-Dados/assets/111309686/669ab75a-7a20-4dfa-891d-f38c09db0647)

Perceba que o "autor" 1 possui 2 telefones diferentes. A fim de normalizar, a coluna "telefone" será removida e cria-se uma nova tabela relacionando o "codAutor" com os telefones. Segue o resultado abaixo:
![image](https://github.com/gldhperes/Resumo-Normalizacao-De-Dados/assets/111309686/6f249930-8365-4803-948b-b4256f208f79)
![image](https://github.com/gldhperes/Resumo-Normalizacao-De-Dados/assets/111309686/1216d5e9-69f6-4ef0-b2bf-a39251b28db9)
