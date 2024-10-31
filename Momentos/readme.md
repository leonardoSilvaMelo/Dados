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

Vamos fazer algumas perguntas para brincar de análise exploratória de dados com MySQL.

* Quantos funcionarios da empresa Momento trabalham no departamento de vendas?
  R: 5

  Q:
  ```sql
  select count(*) from funcionarios where departamento_id like "8";
  ```

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

* Quanto o departamento de Vendas gasta em salários?
  R: '51.500,00'

  Q:
  ```sql
  SELECT SUM(salario) FROM funcionarios WHERE departamento_id = '8';
  ```

* Um novo departamento foi criado. O departamento de Inovações. 
Ele será locado no Brasil. Por favor, adicione-o no banco de dados da empresa colocando quaisquer informações que você achar relevantes.

* O departamento de Inovações está sem funcionários. Inclua alguns colegas de turma nesse departamento.  

* Quantos funcionarios a empresa Momento tem agora?

* Quantos funcionários da empresa Momento possuem conjuges?

* Qual a média salarial dos funcionários da empresa Momento, excluindo-se o CEO?

* Qual a média salarial do departamento de tecnologia? 

* Qual o departamento com a maior média salarial?

* Qual o departamento com o menor número de funcionários?

* Pensando na relação quantidade e valor unitario, qual o produto mais valioso da empresa?

* Qual o produto mais vendido da empresa?

* Qual o produto menos vendido da empresa?

* Qual o funcionário contratado há mais tempo na empresa?

* Qual o funcionário contratado há menos tempo na empresa?
