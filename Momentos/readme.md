<!-- /*SELECT 

	CONCAT(

	funcionarios.primeiro_nome, " ",

    funcionarios.sobrenome) as nome_funcionario,

    cargos.cargo_nome as nome_cargo

FROM funcionarios

INNER JOIN cargos

ON funcionarios.cargo_id = cargos.cargo_id

order by funcionarios.primeiro_nome;
 */ -->

 # Momento 

Contém a base de indicados da empresa Momento para treinar consultas complexas no MySQL.

### Departamento de Tecnologia 

* Inclua suas próprias informações no departamento de Tecnologia da empresa.
  Q:
  ```sql
  INSERT INTO funcionarios(funcionario_id,primeiro_nome,sobrenome,email,senha,telefone,data_contratacao,cargo_id,salario,gerente_id,departamento_id) 
  VALUES (777,'Leonardo','Silva','leonardo.silva@momento.org','@4@8@15@16',NULL,'2024-01-04',20,19650.00,100,6);
  ```

* Agora diga, quantos funcionários temos ao total na empresa?
  R: 42

  Q:
  ```sql
  SELECT COUNT(*) FROM funcionarios;
  ```

* E quanto ao Departamento de Tecnologia?
  R: 6

  Q:
  ```sql
  SELECT COUNT(*) FROM funcionarios WHERE departamento_id = '6';
  ```

### Departamento de Vendas 

* Quantos funcionarios da empresa Momento trabalham no departamento de vendas?
  R: 5

  Q:
  ```sql
  select count(*) from funcionarios where departamento_id like "8";
  ```

* Quanto o departamento de Vendas gasta em salários?
  R: '51.500,00'

  Q:
  ```sql
  SELECT SUM(salario) FROM funcionarios WHERE departamento_id = '8';
  ```

* Quais são os produtos mais vendidos e quais têm pouca ou nenhuma saída?
R: Os produto mais vendidos são o "Uniforme do Superman" e o "Capacete do Homem-Formiga". Já  os produtos com pouca ou nenhuma saída são o 'Laço da Honestidade' e o 'Batarangs Oficiais'.

Q:
```sql
SELECT * FROM vendas ORDER BY quantidade;

SELECT * FROM produtos;
```

* Qual é o produto mais caro no inventário da empresa?
R: Sabre de Luz (Mace Windu)

Q:
```sql
SELECT * FROM produtos ORDER BY produto_price;
```


### Departamento de Inovações 

* **Um novo departamento foi criado. O departamento de Inovações.** 
Ele será locado no Brasil. Por favor, adicione-o no banco de dados da empresa colocando quaisquer informações que você achar relevantes.
R:
```sql
INSERT INTO departamentos(departamento_nome,escritorio_id) 
VALUES ("Inovações",1900);
```

* O departamento de Inovações está sem funcionários. Inclua alguns colegas de turma nesse departamento.
Q:
```sql
INSERT INTO funcionarios(funcionario_id,primeiro_nome,sobrenome,email,senha,telefone,data_contratacao,cargo_id,salario,gerente_id,departamento_id) 
VALUES (55,'Yago','Fera','yago.fera@momento.org','@4@8@15@16','515.124.4569','1994-08-18',7,12000.00,101,18);

INSERT INTO funcionarios(funcionario_id,primeiro_nome,sobrenome,email,senha,telefone,data_contratacao,cargo_id,salario,gerente_id,departamento_id) 
VALUES (66,'Wesley','Safadão','weslet.safadao@momento.org','@4@8@15@16','515.124.4569','1994-08-18',7,12000.00,101,18);
```

### Funcionários

* Quantos funcionários da empresa Momento possuem conjuges?
R: 4

Q:
```sql
SELECT COUNT(*) FROM dependentes where relacionamento = 'Cônjuge';
```

* Qual o funcionário contratado há mais tempo na empresa?
R: Steven Wayne

Q:
```sql
SELECT MIN(data_contratacao) FROM funcionarios;

SELECT * FROM funcionarios WHERE data_contratacao = '1987-06-17';
```

* Qual o funcionário contratado há menos tempo na empresa?
R: Zatana Zatara

Q:
```sql
SELECT MAX(data_contratacao) FROM funcionarios;

SELECT * FROM funcionarios WHERE data_contratacao = '2000-01-04';
```

* Quem são os funcionários com mais tempo na empresa, considerando a `data_contratacao`?
R: Steven Wayne e Jennifer Whalen

Q:
```sql
SELECT COUNT(*) FROM funcionarios WHERE data_contratacao LIKE '%1987%'
```

* Como a média salarial dos funcionários da "Momento" evoluiu nos últimos anos?
Q:
```sql
SELECT AVG(salario), year(data_contratacao) as data_y FROM funcionarios
GROUP BY data_contratacao
order by data_y;
```
