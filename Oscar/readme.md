# Nomeados ao Oscar

Contém a base de indicados ao Oscar em formato JSON para treinar comandos de consulta no MongoDB. 

* Quantas vezes Natalie Portman foi indicada ao Oscar?

R: 3 vezes

Q:
```sql
SELECT COUNT(*) FROM indicados_ao_oscar WHERE "Name" Like "%Natalie Portman%";
```

* Quantos Oscars Natalie Portman ganhou?

R:1

Q:
```sql
SELECT COUNT(*) FROM indicados_ao_oscar WHERE "Name" Like "%Natalie Portman%" AND vencedor = "true";
```

* Amy Adams já ganhou algum Oscar?

R:Não

Q:
```sql
SELECT * FROM indicados_ao_oscar WHERE "Name" Like "%Amy Adams%";
```

* A série de filmes Toy Story ganhou um Oscar em quais anos?

R:Nenhum

Q:
```sql
SELECT ano_cerimonia FROM indicados_ao_oscar WHERE nome_do_filme = "toy story%" AND vencedor = "true";

```

* A partir de que ano que a categoria "Actress" deixa de existir?

R:1977

Q:
```sql
SELECT * FROM indicados_ao_oscar Where categoria = "ACTRESS";
```

* Quem ganhou o primeiro Oscar para Melhor Atriz? Em que ano?

R:Janet Gaynor no ano de 1928

Q:
```sql
SELECT * FROM indicados_ao_oscar WHERE categoria= "ACTRESS" AND vencedor = "true";
```

* Na campo "Vencedor", altere todos os valores com "true" para 1 e todos os valores "false" para 0.

R: true = 1 e false = 2.

Q:
``sql
UPDATE indicados_ao_oscar
SET vencedor = "1"
WHERE vencedor = "true";

UPDATE indicados_ao_oscar
SET vencedor = "0"
WHERE vencedor = "false";
``

* Em qual edição do Oscar "Crash" concorreu ao Oscar?

R: 78

Q:
```sql
SELECT * FROM indicados_ao_oscar WHERE nome_do_filme = "Crash";
```

* O filme Central do Brasil aparece no Oscar?

R: Sim

Q:
```sql
select * from indicados_ao_oscar where nome_do_filme = "central station";
```

* Inclua no banco 3 filmes que nunca foram nem nomeados ao Oscar, mas que merecem ser.

Q:
```sql
INSERT INTO indicados_ao_oscar(ano_filmagem,ano_cerimonia,cerimonia,categoria,nome_do_indicado,nome_do_filme,vencedor) 
VALUES (2004,2005,3,'Melhor Filme de Animação','Stephen Hillenburg','Bob Esponja: O Filme','true');

INSERT INTO indicados_ao_oscar(ano_filmagem,ano_cerimonia,cerimonia,categoria,nome_do_indicado,nome_do_filme,vencedor) 
VALUES (2015,2016,3,'Melhor Filme de Animação','Stephen Hillenburg','Bob Esponja: Um Herói Fora d. Água','true');

INSERT INTO indicados_ao_oscar(ano_filmagem,ano_cerimonia,cerimonia,categoria,nome_do_indicado,nome_do_filme,vencedor) 
VALUES (2019,2020,3,'Melhor Filme de Animação','Maurício de Sousa Produções','Turma da Mônica: O Filme','true');
```

* Denzel Washington já ganhou algum Oscar?

R:Não

Q:
```sql
select * from indicados_ao_oscar where nome_do_indicado = "Denzel Washington" and vencedor = "true";
```

* Quais os filmes que ganharam o Oscar de Melhor Filme?

R:Nenhum

Q:
```sql
select nome_do_indicado, nome_do_filme, vencedor from indicados_ao_oscar where categoria = "best picture" and vencedor = "true";
```
