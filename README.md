Muito bem, Pessoal...
Hoje vamos trabalhar com o Oscar. A ideia de premiar ou ser premiado é para reconhecer:
Reconhecer uma qualidade
Reconhecer um atributo
Reconhecer o esforço...
Reconhecer sempre.
Nem todos os prêmios são merecidos e nem todos que merecem ganham. Então vale mesmo a pena, premiar?
USO DOS COMANDOS SQL
1)-Quantas vezes Natalie Portman foi indicada ao Oscar? R: Ela foi indicadas 3 vezes. QUERY EM SQL SELECT COUNT(*) FROM oscar WHERE name LIKE '%Natalie Portman%';

2)-Quantos Oscars Natalie Portman ganhou? R: Ela venceu uma vez. QUERY EM SQL SELECT COUNT(*) FROM oscar WHERE name LIKE '%Natalie Portman%' AND winner LIKE '%True%';

3)-Amy Adams já ganhou algum Oscar? R: Ela nunca venceu. QUERY EM SQL SELECT COUNT(*) FROM oscar WHERE name LIKE '%Amy Adams%' AND winner LIKE '%True%';

4)-Alguém já ganhou um Oscar e tem o seu primeiro nome?? R: Não

QUERY EM SQL SELECT COUNT(*) FROM oscar WHERE name LIKE '%Diego%' AND winner LIKE '%True%';

5)-Toy Story 3 ganhou um Oscar em quais anos?/b> R: 2011 QUERY EM SQL SELECT name, year_film FROM oscar WHERE film LIKE '%Toy Story 3%' AND winner LIKE '%True%';

6)-Quem tem mais Oscars: a categoria "Melhor Ator" ou "Melhor Filme"?</b R: Melhor Ator

QUERY EM SQL SELECT category, COUNT(category) FROM oscar WHERE category LIKE '%ACTOR' OR category LIKE '%CINEMATOGRAPHY' AND winner LIKE '%True%' GROUP BY category;

7)-O primeiro Oscar para melhor Atriz foi para quem? Em que ano?/b> R: Janet Gaynor em 1928 QUERY EM SQL SELECT name, MIN(year_ceremony) FROM oscar WHERE category LIKE '%ACTRESS%' AND winner LIKE '%True%';

8)-Na categoria Winner, altere todos os valores com "True" para 1 e todos os valores "False" para 0./b> R: UPDATE oscar SET winner = '1' WHERE winner LIKE '%True%' R: UPDATE oscar SET winner = '0' WHERE winner LIKE '%False%'

9)-Em qual edição do Oscar "Crash" ganhou o prêmio? R: Em 2006 QUERY EM SQL SELECT year_ceremony FROM oscar WHERE film LIKE '%Crash' AND winner LIKE '%1%';

10)-Que filme merecia ganhar um Oscar e não ganhou? R: Joker

11)-Bom... dê um Oscar para esse filme, então. R: UPDATE oscar SET winner = '1' WHERE id = 10294

12)-O filme Central do Brasil aparece no Oscar? R: Não QUERY EM SQL SELECT * FROM oscar WHERE film LIKE '%Central do Brasil';

13)-Aliás... Qual sua opinião sobre central do Brasil R: Nunca assisti ,as vou colocar na minha base de dados

14)-Inclua no banco 7 filmes que nunca nem foram nomeados ao Oscar, mas que na sua opinião, merecem. R: INSERT INTO oscar (year_film, category, name, film, winner) VALUES ('1980', 'CINEMATOGRAPHY', 'Charles Chaplin', 'Tempos Modernos', '0'), ('1980', 'CINEMATOGRAPHY', 'Stanley Kubrick', 'O Iluminado', '0'), ('1988', 'CINEMATOGRAPHY', 'Hayao Miyazaki', 'Meu Amigo Totoro', '0'), ('1993', 'CINEMATOGRAPHY', 'Harold Ramis', 'Feitiço do Tempo', '0'), ('1997', 'CINEMATOGRAPHY', 'Hayao Miyazaki', 'Princesa Mononoke', '0'), ('2016', 'CINEMATOGRAPHY', 'Makoto Shinkai', 'Your Name', '0'), ('2017', 'CINEMATOGRAPHY', 'Patty Jenkins', 'Mulher-Maravilha', '0');

15)-Crie uma nova categoria de premiação. Qualquer prêmio que você queira dar. Agora vamos dar esses prêmios aos filmes que você cadastrou na questão acima. R: ALTER TABLE oscas ADD curto BINARY; R: UPDATE oscar SET curto = 1 WHERE id BETWEEN 10396 AND 10403;

16)-Qual foi o primeiro ano a ter um prêmio do Oscar?. R: Em 1928 QUERY EM SQL SELECT MIN(year_ceremony) FROM oscar;

17)-Pensando no ano em que você nasceu: Qual foi o Oscar de melhor filme, Melhor Atriz e Melhor Diretor? R: Melhor atriz foi: Louise Dresser Melhor filme foi: Crouching Tiger, Hidden Dragon Melhor diretor foi: Steven Soderbergh QUERY EM SQL SELECT name, film, category FROM oscar WHERE category LIKE '%CINEMATOGRAPHY' OR category LIKE '%ACTRESS' OR category LIKE '%DIRECTING' AND winner LIKE '%1%' AND year_ceremony = '2001' GROUP BY category;

18)-Agora procure 7 atrizes que não sejam americanas, europeias ou brasileiras. Vamos cadastrá-los no nosso banco, mas eles ainda não ganharam o Oscar. Só foram nomeados. R: INSERT INTO oscar (name) VALUES ('Cameron Diaz'), ('Drew Barrymore'), ('Sarah Polley'), ('Emily Blunt'), ('Robin Wright'), ('Charlotte Gainsbourg'), ('Kirsten Dunst');

20)-Utilizando o comando 'Alter Table', troque os tipos dos dados da coluna/campo "Winner" para Bit. R: ALTER TABLE oscar MODIFY COLUMN winner BINARY;

