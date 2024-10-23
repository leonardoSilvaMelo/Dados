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
```
SELECT * FROM indicados_ao_oscar WHERE "Name" Like "%Amy Adams%";
```

* A série de filmes Toy Story ganhou um Oscar em quais anos?

R:Nenhum

Q:
```
SELECT ano_cerimonia FROM indicados_ao_oscar WHERE nome_do_filme = "toy story%" AND vencedor = "true";

```

* A partir de que ano que a categoria "Actress" deixa de existir?

R:1977

Q:
```
SELECT * FROM indicados_ao_oscar Where categoria = "ACTRESS";
```

* Quem ganhou o primeiro Oscar para Melhor Atriz? Em que ano?

R:Janet Gaynor no ano de 1928

Q:
```
SELECT * FROM indicados_ao_oscar WHERE categoria= "ACTRESS" AND vencedor = "true";
```

* Na campo "Vencedor", altere todos os valores com "true" para 1 e todos os valores "false" para 0.

R: true = 1 e false = 2.

Q:
``
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
```
SELECT * FROM indicados_ao_oscar WHERE nome_do_filme = "Crash";
```

* O filme Central do Brasil aparece no Oscar?

R: Sim

Q:
```
select * from indicados_ao_oscar where nome_do_filme = "central station";
```

* Inclua no banco 3 filmes que nunca foram nem nomeados ao Oscar, mas que merecem ser. 

* Denzel Washington já ganhou algum Oscar?

R:Não

Q:
```
select * from indicados_ao_oscar where nome_do_indicado = "Denzel Washington" and vencedor = "true";
```

* Quais os filmes que ganharam o Oscar de Melhor Filme?

R:Nenhum

Q:
```
select nome_do_indicado, nome_do_filme, vencedor from indicados_ao_oscar where categoria = "best picture" and vencedor = "true";
```

* Bonus: Quais os filmes que ganharam o Oscar de Melhor Filme e Melhor Diretor na mesma cerimonia?

* Bonus: Denzel Washington e Jamie Foxx já concorreram ao Oscar no mesmo ano?