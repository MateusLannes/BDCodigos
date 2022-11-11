# BDCodigos


 - Links para utilizar - 
 https://docs.aws.amazon.com/pt_br/redshift/latest/dg/r_EXTRACT_function.html
 https://docs.aws.amazon.com/pt_br/redshift/latest/dg/r_Dateparts_for_datetime_functions.html
 https://www.devmedia.com.br/introducao-ao-sql-data-e-hora/17005



 - Testes para BD 
UPDATE logradouro set complemento = 5
where complemento = 'Residencial' 
and fk_tipo_logradouro = 7;

alter Table logradouro RENAME COLUMN complemento to fk_id_complemento;
SELECT * FROM "public"."logradouro" LIMIT 100;

CREATE TABLE COMPLEMENTO (
    id SERIAL PRIMARY KEY,
    complemento VARCHAR(45)
);


INSERT INTO complemento (complemento)
VALUES
('Edificio'),
('Casa'),
('Bloco'),
('apartamento'),
('Residencial');

select nome, extract(id FROM id) as id_complemento
from logradouro where id > 2 ;

select data_nasc from usuario;

SELECT  nome, data_nasc FROM usuario
WHERE data_nasc BETWEEN '2000-01-01' AND CURRENT_DATE;


SELECT EXTRACT (decade FROM data_nasc) FROM usuario;


/*
1990-06-20
2006-05-13
2015-06-28
2003-03-08
2000-10-18
1993-03-01
2007-01-01
1994-08-27
2006-11-03
2001-01-11
1987-12-01
1999-01-27
1981-07-11
1977-02-06
1988-11-02
*/