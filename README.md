
# Boas vindas ao repositório do projeto All For One


# Entregáveis

<details>
  <summary><strong>👨‍💻 O que deverá ser desenvolvido</strong></summary><br />

Hoje você fará um projeto com o codinome _All For One_ em que praticará todos os conceitos de SQL já ensinados até aqui. Porém, você vai usar um banco de dados totalmente diferente, então dê tchau para o `sakila` e dê boas vindas ao `Northwind`, que será usado neste projeto. As instruções de como restaurar o banco podem ser lidas a seguir.
</details>

<details>
  <summary><strong>👨‍💻 Desenvolvimento</strong></summary><br />

Temos, nesse projeto, uma série de desafios com diferentes níveis de complexidade que devem ser resolvidos cada um em seu arquivo próprio.

1. Leia a pergunta e crie na raiz do projeto um arquivo chamado desafioN.sql, em que N é o número do desafio;

2. O arquivo deve conter apenas o código SQL do desafio resolvido. **Não se esqueça de incluir o ponto e vírgula (";")** no final de suas queries e **não coloque o nome do banco de dados na query**. O exemplo a seguir é a forma correta:

```sql
SELECT * FROM orders;
```

3. Faça isso até finalizar todos os desafios.

4. Para entregar o seu projeto você deverá criar um _Pull Request_ neste repositório. Este _Pull Request_ deverá conter os arquivos `desafio1.sql`, `desafio2.sql` e assim por diante até o `desafio27.sql`, que conterão seu código `SQL` de cada desafio, respectivamente.

5. **Não utilizem** `USE northwind` no início dos seus arquivos.

6. Após a execução dos teste locais, o banco de dados `northwind` é recriado.

7. Não esqueçam dos easter Eggs: IUzI1NiJ9.eyJyZWFkbWUiOiJNY

 </details>

# Orientações

<details>
  <summary><strong>:whale: Rodando no Docker vs Localmente</strong></summary><br />

## Com Docker

  **:warning: Antes de começar, seu docker-compose precisa estar na versão 1.29 ou superior. [Veja aqui](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04-pt) ou [na documentação](https://docs.docker.com/compose/install/) como instalá-lo. No primeiro artigo, você pode substituir onde está com `1.26.0` por `1.29.2`.**

  > :information_source: Rode os serviços `node` e `db` com o comando `docker-compose up -d`.

- Lembre-se de parar o `mysql` se estiver usando localmente na porta padrão (`3306`), ou adapte, caso queria fazer uso da aplicação em containers
- Esses serviços irão inicializar um container chamado `all_for_one` e outro chamado `all_for_one_db`.
- A partir daqui você pode rodar o container `all_for_one` via CLI ou abri-lo no VS Code.

  > :information_source: Use o comando `docker exec -it all_for_one bash`.

- Ele te dará acesso ao terminal interativo do container criado pelo compose, que está rodando em segundo plano.
- As credencias de acesso ao banco de dados estão definidas no arquivo `docker-compose.yml`, e são acessíveis no container através das variáveis de ambiente `MYSQL_USER` e `MYSQL_PASSWORD`. 💡

  > :information_source: Instale as dependências [**Caso existam**] com `npm install`. (Instale dentro do container)

- **:warning: Atenção:** Caso opte por utilizar o Docker, **TODOS** os comandos disponíveis no `package.json` (npm start, npm test, npm run dev, ...) devem ser executados **DENTRO** do container, ou seja, no terminal que aparece após a execução do comando `docker exec` citado acima.

- **:warning: Atenção:** O **git** dentro do container não vem configurado com suas credenciais. Ou faça os commits fora do container, ou configure as suas credenciais do git dentro do container.

- **:warning: Atenção:** Não rode o comando npm audit fix! Ele atualiza várias dependências do projeto, e essa atualização gera conflitos com o avaliador.

  <br />

## Sem Docker

  > :information_source: Instale as dependências [**Caso existam**] com `npm install`

- **:warning: Atenção:** Não rode o comando npm audit fix! Ele atualiza várias dependências do projeto, e essa atualização gera conflitos com o avaliador.

- **✨ Dica:** Para rodar o projeto desta forma, obrigatoriamente você deve ter o `node` instalado em seu computador.
- **✨ Dica:** O avaliador espera que a versão do `node` utilizada seja a 16.

  <br/>

</details>


  ---

# Requisitos do projeto

Monte queries para encontrar as informações esperadas pelos desafios.

- **:warning: Atenção:** Não é necessário colocar `USE northwind` ou `SET SQL_SAFE_UPDATES = 0;` no início dos seus arquivos

- **:warning: Atenção:** Os testes são executados em uma cópia do banco de dados, o `northwind_tests`. Por isto as _querys_  devem indicar somente o nome da tabela, e não utilizar o formato `db.table`.

- Exemplo de query `correta`: SELECT product_name FROM products;

- Exemplo de query `incorreta`: SELECT product_name FROM northwind.products;


## Desafios Iniciais

1 - Exiba apenas os nomes dos produtos na tabela `products`.

  ---

2 - Exiba os dados de todas as colunas da tabela `products`.

  ---

3 - Escreva uma query que exiba os valores da coluna que representa a _primary key_ da tabela `products`.

  ---

4 - Conte quantos registros existem na coluna `product_name` da tabela `products`.

  ---

5 - Monte uma query que exiba os dados da tabela `products` a partir do quarto registro até o décimo terceiro.

<details>
  <summary>&nbsp;&nbsp;<strong>👀 Observações técnicas</strong></summary>

- Tanto o quarto quanto o décimo terceiro registros, precisam aparecer na consulta;

- Não use `where` ou `order by`.

  <br />

</details>

  ---

6 - Exiba os dados das colunas `product_name` e `id` da tabela `products` de maneira que os resultados estejam em ordem alfabética dos nomes.

  ---

7 - Mostre apenas os ids dos 5 últimos registros da tabela `products` (a ordenação deve ser baseada na coluna `id`).

  ---

8 - Faça uma consulta na tabela `employees` que retorne o nome completo da pessoa colaboradora (colunas `first_name` e `last_name`) com o nome `full_name` e também a localização completa (colunas `city`, `state_province` e `address`) com o nome `location`.

<details>
  <summary>&nbsp;&nbsp;<strong>👀 Observações técnicas</strong></summary>

- Na primeira coluna, exiba a concatenação de `first_name` e `last_name` com o nome `full_name` separados por um espaço.

- Na segunda coluna, exiba a concatenação de `city`, `state_province` e `address` com o nome `location`.

- A concatenação de `city` e `state_province` deve ser separada por um hífen, e a coluna `address` deve ser separada por uma vírgula e um espaço. Exemplo:

    ```text
      "Seatle-WA, 123 1st Avenue"
    ```

  <br />

</details>

## Desafios sobre filtragem de dados

9 - Mostre todos os valores de `notes` da tabela `purchase_orders` que não são nulos.

  ---

10 - Mostre todos os dados da tabela `purchase_orders` em ordem decrescente, ordenados por `created_by` em que o `created_by` é maior ou igual a 3.

- Ordene também os resultados pelo `id` de forma crescente, como critério de desempate para a ordenação.

  ---

11 - Exiba os dados da coluna `notes` da tabela `purchase_orders` em que seu valor de `Purchase generated based on Order` é maior ou igual a 30 e menor ou igual a 39.

- ✨ Dica: `Purchase generated based on Order` é um valor atribuído à coluna `notes` e não uma coluna.

  ---

12 - Mostre as `submitted_date` de `purchase_orders` em que a `submitted_date` é do dia 26 de abril de 2006.

  ---

13 - Mostre o `supplier_id` das `purchase_orders` em que o `supplier_id` seja 1 ou 3.

  ---

14 - Mostre os resultados da coluna `supplier_id` da tabela `purchase_orders` em que o `supplier_id` seja maior ou igual a 1 e menor ou igual 3.

  ---

15 - Mostre somente as horas (sem os minutos e os segundos) da coluna `submitted_date` de todos registros da tabela `purchase_orders`.

- No resultado, a hora extraída da coluna `submitted_date` deve ser chamada de `submitted_hour`.

  ---

16 - Exiba a `submitted_date` das `purchase_orders` que estão entre `2006-01-26 00:00:00` e `2006-03-31 23:59:59`.

  ---

17 - Mostre os registros das colunas `id` e `supplier_id` das `purchase_orders` em que os `supplier_id` sejam tanto 1, ou 3, ou 5, ou 7.

  ---

18 - Mostre todos os registros de `purchase_orders` que tem o `supplier_id` igual a 3 e `status_id` igual a 2.

  ---

19 - Mostre a quantidade de pedidos que foram feitos na tabela `orders` pelo `employee_id` igual a 5 ou 6, e que foram enviados através do método(coluna) `shipper_id` igual a 2.

- No resultado, a coluna que contém a contagem de pedidos deve ser chamada de `orders_count`.

  ---

## Desafios de manipulação de tabelas

20 - Adicione à tabela `order_details` um registro com `order_id`: 69, `product_id`: 80, `quantity`: 15.0000, `unit_price`: 15.0000, `discount`: 0, `status_id`: 2, `date_allocated`: NULL, `purchase_order_id`: NULL e `inventory_id`: 129.

- ✨ Dica: O `id` deve ser incrementado automaticamente. Para entender melhor isso, você pode consultar o arquivo de criação da tabela (./northwind.sql, na linha 439) [aqui](northwind.sql).

  ---

21 - Adicione com um único `INSERT`, duas linhas à tabela `order_details` com os mesmos dados do requisito 20.

<details>
  <summary>&nbsp;&nbsp;<strong>👀 Observações técnicas</strong></summary>
  
- Esses dados são novamente `order_id`: 69, `product_id`: 80, `quantity`: 15.0000, `unit_price`: 15.0000, `discount`: 0, `status_id`: 2, `date_allocated`: NULL, `purchase_order_id`: NULL e `inventory_id`: 129;

- O `ìd` deve ser incrementado automaticamente.

  <br />

</details>

  ---

22 - Atualize todos os dados da coluna `discount`, na tabela `order_details`, para 15.

⚠️ Para testar localmente, pode ser necessário utilização do SAFE UPDATE, porém **não é necessário adicionar a instrução do SAFE UPDATE no arquivo `desafio22.sql` junto a query**, pois o próprio avaliador irá ajustar isso.

  ---

23 - Atualize os dados da coluna `discount` da tabela `order_details` para 30, onde o valor na coluna `unit_price` seja menor que 10.0000.

- ✨ Dica: Não é necessário utilizar o SAFE UPDATE em sua query.

  ---

24 - Atualize os dados da coluna `discount` da tabela `order_details` para 45, onde o valor na coluna `unit_price` seja maior que 10.0000 e o id seja um número entre 30 e 40.

- ✨ Dica: Não é necessário utilizar o SAFE UPDATE em sua query.

  ---

25 - Delete todos os dados em que a `unit_price` da tabela `order_details` seja menor que 10.0000.

  ---

26 - Delete todos os dados em que a `unit_price` da tabela `order_details` seja maior que 10.0000.

  ---

27 - Delete todos os dados da tabela `order_details`.

---
