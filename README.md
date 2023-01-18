# paises-minerios
AC1 usando MySQL
# CREATE

drop database if exists paises_minerios;
create database paises_minerios;
use paises_minerios;

create table paises (
id int primary key not null auto_increment,
paises_nome varchar (30) not null,
capitais varchar (30) not null,
moedas varchar (30) not null,
id_cont int not null
);

create table minerios (
id int primary key not null auto_increment,
minerios_nome varchar (30) not null
);

create table continentes (
id int primary key not null auto_increment,
cont_nome varchar (30) not null,
area decimal (30,2),
vulc_ativ int
);

create table fabricacao (
id int primary key not null auto_increment,
id_minerios int,
id_paises int,
peso decimal (30,2),
ano int
);

alter table paises
add constraint foreign key (id_cont) references continentes(id);

alter table fabricacao
add constraint foreign key (id_paises) references paises(id);

alter table fabricacao
add constraint foreign key (id_minerios) references minerios(id);

insert into continentes (cont_nome, area, vulc_ativ) values 
('America', 4255000.00, 25),
('Oceania', 8526000.00, 5),
('África', 3037000.00, 15),
('Ásia', 4567800.00, 10);

insert into paises (paises_nome, capitais, moedas, id_cont) values
('EUA', 'Washington', 'Dólar', 1),
('Nova Zelândia', 'Wellington', 'Dólar', 2),
('Angola', 'Luanda', 'Kwanza', 3),
('Japão', 'Tóquio', 'Iene', 4),
('Tailândia', 'Bangkok', 'Baht', 2),
('Groenlândia', 'Nuuk', 'Coroa dinamarquesa', 1),
('Cazaquistão', 'Astana', 'Tenge', 4),
('Afeganistão', 'Kabul', 'Afegane', 4),
('Suazilândia', 'Lobamba', 'Rand', 3),
('Turcomenistão ', 'Asgabate', 'Manat turcomano', 4);

insert into minerios (minerios_nome) values
('Silício'),
('Ferro'), 
('Bauxita'), 
('Diamante'), 
('Ouro'), 
('Tungstênio'), 
('Alumínio'), 
('Potássio'), 
('Rubídio'),
('Mercúrio'),
('Frâncio'),
('Bário'),
('Cálcio'),
('Cobre'),
('Magnésio');

insert into fabricacao (id_paises, id_minerios, peso, ano) values
(1, 6, 6514785.00 , 2021),
(2, 6, 1234567.00 , 2021),
(3, 6, 3985478.00 , 2021),
(4, 6, 8524785.00 , 2021),
(5, 6, 6957785.00 , 2021),
(6, 6, 4004785.00 , 2021),
(7, 6, 1594785.00 , 2021),
(8, 6, 6544785.00 , 2021),
(1, 1, 3055200.00, 2020),
(2, 1, 1234567.00 , 2020),
(3, 1, 3985478.00 , 2020),
(4, 1, 8524785.00 , 2020),
(5, 1, 6957785.00 , 2020),
(6, 1, 4004785.00 , 2020),
(7, 1, 1594785.00 , 2020),
(8, 1, 6544785.00 , 2020),
(1, 4, 3055200.00 , 2012),
(2, 4, 8555200.00 , 2012),
(3, 4, 3578490.00 , 2012),
(4, 4, 3075200.00 , 2012),
(5, 4, 1595275.00 , 2012),
(6, 4, 7589641.00 , 2012),
(7, 4, 8549652.00 , 2012),
(8, 4, 4002892.00 , 2012),
(1, 1, 6544785.00 , 2014),
(2, 2, 2454785.00 , 2014),
(3, 3, 3674785.00 , 2014),
(4, 4, 4594785.00 , 2014),
(5, 3, 1594785.00 , 2014),
(6, 6, 1264785.00 , 2014),
(7, 7, 7534785.00 , 2014),
(8, 8, 9514785.00 , 2014),
(1, 6, 6544785.00 , 2014),
(2, 7, 2454785.00 , 2014),
(3, 11, 3674785.00 , 2014),
(4, 5, 4594785.00 , 2014),
(5, 1, 1594785.00 , 2014),
(6, 4, 1264785.00 , 2014),
(7, 15, 7534785.00 , 2014),
(8, 15, 9514785.00 , 2014),
(4, 6, 8745785.00 , 2014),
(1, 7, 9634785.00 , 2014),
(2, 5, 7414785.00 , 2014),
(3, 11, 1594785.00 , 2014),
(5, 1, 4564785.00 , 2014),
(7, 4, 2584785.00 , 2014),
(2, 15, 8524785.00 , 2014),
(8, 15, 1785495.00 , 2014),
(3, 2, 9654875.00 , 2014),
(4, 2, 2000000.00 , 2019),
(2, 2, 5000000.00 , 2019),
(6, 2, 4000750.00 , 2019),
(1, 2, 3950000.00 , 2019),
(3, 2, 2500000.00 , 2019),
(2, 1, 8555200.00 , 2010),
(2, 1, 8555200.00 , 2008),
(3, 1, 3578490.00 , 2007),
(4, 1, 3075200.00 , 2006),
(5, 1, 1595275.00 , 2004),
(6, 1, 7589641.00 , 2008),
(7, 1, 8549652.00 , 2004),
(1, 1, 6485200.00 , 2010),
(2, 1, 9655200.00 , 2010),
(3, 1, 3578490.00 , 2010),
(4, 1, 3075200.00 , 2010),
(5, 1, 1595275.00 , 2010),
(6, 1, 7589641.00 , 2010),
(7, 1, 8549652.00 , 2010),
(8, 1, 4002892.00 , 2010),
(3, 2, 3500420.00 , 2019),
(4, 4, 6584200.00 , 2012),
(5, 4, 9514875.00 , 2012),
(6, 4, 9632641.00 , 2012),
(7, 4, 8529652.00 , 2012),
(1, 4, 9514785.00 , 2018),
(1, 7, 8524785.00 , 2018),	
(3, 8, 9515985.00 , 2018),
(5, 5, 1458785.00 , 2018),
(7, 15, 6514785.00 , 2018),
(2, 3, 1234567.00 , 2011),
(6, 3, 3985478.00 , 2011),
(4, 3, 8524785.00 , 2011),
(1, 3, 6957785.00 , 2011),
(2, 3, 4004785.00 , 2011),
(8, 3, 1594785.00 , 2011),
(5, 4, 1234875.00 , 2014),
(1, 1, 3055200.00 , 2014),
(2, 1, 8555200.00 , 2014),
(3, 1, 3578490.00 , 2014),
(4, 1, 3075200.00 , 2014),
(3, 3, 3674785.00 , 2014),
(5, 4, 1234875.00 , 2012),
(2, 1, 8555200.00 , 2019),
(3, 1, 3578490.00 , 2019),
(4, 1, 3075200.00 , 2019),
(3, 3, 3674785.00 , 2019),
(4, 4, 4594785.00 , 2019),
(5, 3, 1594785.00 , 2019),
(6, 6, 1264785.00 , 2019),
(1, 5, 6514785.00 , 2021),
(2, 5, 1234567.00 , 2021),
(3, 5, 3985478.00 , 2021),
(4, 5, 8524785.00 , 2021),
(5, 5, 6957785.00 , 2021),
(1, 1, 3055200.00 , 2009);

# RELATÓRIOS

-- 1 - Um relatório que mostra todos os países de um continente, informando o nome do país, sua capital e moeda oficial.
select paises_nome Paises, c.cont_nome Continentes, capitais, moedas from paises as p
join continentes as c
on p.id_cont = c.id
where id_cont = 4;

-- 2 - O total de silício produzido na década de 2010 de cada país.
select  pa.paises_nome Paises, m.minerios_nome Minérios, sum(peso) as Peso from fabricacao as fabri
join paises as pa on fabri.id_paises = pa.id
join minerios as m on fabri.id_minerios = m.id
where ano between 2010 and 2019
and m.minerios_nome = 'Silício' 
group by pa.paises_nome, m.minerios_nome
order by ano asc;

-- 3 - Todos os países que em 2019 registraram produção de ferro entre 2000000 e 5000000 de toneladas.
select pa.paises_nome Paises, ano Ano, peso Peso, m.minerios_nome Minérios from fabricacao as fabri
join paises as pa on fabri.id_paises = pa.id
join minerios as m on fabri.id_minerios = m.id
where ano = 2019
and peso between  2000000.00 and 5000000.00
and m.minerios_nome = 'Ferro';

-- 4 - Todos os continentes informando seu nome, área e quantidade vulcões ativos.
select cont_nome Continentes, area Área, vulc_ativ Vulcões_Ativos from continentes;

-- 5 - O pais com maior produção de bauxita em 2011.
select m.minerios_nome Minérios, p.paises_nome Paises, peso, ano from fabricacao as fabri
join paises as p on fabri.id_paises = p.id
join minerios as m on fabri.id_minerios = m.id
where id_minerios = 3
and ano = 2011
and peso = (select max(peso) from fabricacao as fabri
where id_minerios = 3
and ano = 2011);

-- 6 - A média mundial de produção de diamante em 2012.
select minerios.minerios_nome Minérios, avg(peso) as Média, ano from fabricacao
join minerios on fabricacao.id_minerios = minerios.id
where id_minerios = 4
and ano = 2012;

-- 7 - O minério com maior produção em 2018.
select minerios.minerios_nome Minérios, paises.paises_nome Paises, peso, ano from fabricacao
join paises on fabricacao.id_paises = paises.id
join minerios on fabricacao.id_minerios = minerios.id
where ano = 2018
and peso = (select max(peso) from fabricacao
where ano = 2018);

-- 8 - A média de produção de cada minério em 2014.
select minerios.minerios_nome Minérios, avg(peso) as Média, ano from fabricacao
join minerios on fabricacao.id_minerios = minerios.id
and ano = 2014
group by minerios.minerios_nome;

-- 9 - Todos os países que o nome termina com 'istão' ou 'lândia'.
select paises_nome Paises from paises
where paises_nome like '%istão' 
or paises_nome like '%lândia';

-- 10 - Todos os países que produzem ouro e tungstênio no ano passado bem como as quantidades.
select paises.paises_nome Paises, minerios.minerios_nome Minérios, peso from fabricacao
join paises on fabricacao.id_paises = paises.id
join minerios on fabricacao.id_minerios = minerios.id
where ano = 2021
and id_minerios = 5 or id_minerios = 6;


