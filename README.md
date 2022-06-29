# Momento-e-seus-funcionarios<h1>
A Momento é uma empresa única que faz o melhor que pode para alcançar o melhor da humanidade. Nessa atividade tive de manipular um banco de dados de uma empresa ficticia
Atividade Proposta pelo professor Gabriel Augusto, do Curso PROAPROFISSÃO Desenvolvedor Web Java.
##

1 - Inclua suas próprias informações no departamento de tecnologia da empresa.

R: INSERT INTO funcionarios (`primeiro_nome`, `sobrenome`, `email`, `telefone`, `dataContratacao`, `ocupacao_id`, `salario`, `departamento_id`) VALUES ('Thiago','Antenor','thiagoantenor31@gmaill.com','0000 0000','2022-06-29',9,4000.00,6);
##

2 - A administração está sem funcionários. Inclua os outros elementos do seu grupo do demoday no departamento de administração.

R:

INSERT INTO funcionarios(primeiro_nome,sobrenome,email,telefone,dataContratacao,ocupacao_id,salario,gerente_id,departamento_id) VALUES ('Ellen','Silva','ellensilvateixei@momento.org','01011010101','2022-06-29',3,24000.00,NULL,1);

INSERT INTO funcionarios(primeiro_nome,sobrenome,email,telefone,dataContratacao,ocupacao_id,salario,gerente_id,departamento_id) VALUES ('Daniele','Simões','danielesimoes@momento.org','01011010101','2022-06-29',3,24000.00,NULL,1);

INSERT INTO funcionarios(primeiro_nome,sobrenome,email,telefone,dataContratacao,ocupacao_id,salario,gerente_id,departamento_id) VALUES ('Jonathan','Silva','johnconceicao@momento.org','01011010101','2022-06-29',3,24000.00,NULL,1);

INSERT INTO funcionarios(primeiro_nome,sobrenome,email,telefone,dataContratacao,ocupacao_id,salario,gerente_id,departamento_id) VALUES ('Leonardo','Vinicius','leonardopoker25@momento.org','01011010101','2022-06-29',3,24000.00,NULL,1);

INSERT INTO funcionarios(primeiro_nome,sobrenome,email,telefone,dataContratacao,ocupacao_id,salario,gerente_id,departamento_id) VALUES ('Gustavo','Amorim','gutola@momento.org','01011010101','2022-06-29',3,24000.00,NULL,1);

INSERT INTO funcionarios(primeiro_nome,sobrenome,email,telefone,dataContratacao,ocupacao_id,salario,gerente_id,departamento_id) VALUES ('Gabriel','Marques','marques@momento.org','01011010101','2022-06-29',3,24000.00,NULL,1);

##
3 - Agora diga, quantos funcionários temos ao total na empresa?*

R: 50 funcionários

SELECT COUNT(*) FROM `funcionarios`;
##
4- Quantos funcionários temos no departamento de finanças?*

R: 6 funcionarios

SELECT * FROM funcionarios WHERE departamento_id = 10;
##

5 - Qual a média salarial do departamento de tecnologia?*

R: 5466.67

SELECT AVG(salario) FROM funcionarios WHERE departamento_id = 6;
##

6 - Quanto o departamento de Transportes gasta em salários?*

R: O departamento de transportes gasta 41200.00 em salários;

SELECT SUM(PONTOS) AS total FROM tabela;

##

7 - Um novo departamento foi criado. O departamento de inovações. Ele será locado no Brasil. Por favor, adicione-o no banco de dados.

R: INSERT INTO `departamento`(`departamento_id`, `departamento_name`, `posicao_id`) VALUES (12,'Inovações',5400);

##

8 - Novos Funcionários!
Três novos funcionários foram contratados para o departamento de inovações. Por favor, adicione-os: William Ferreira, casado com Inara Ferreira, possui um filho chamado Gabriel que tem 4 anos e adora brincar com cachorros. Ele será programador.Já a Fernanda Lima, que é casada com o Rodrigo, não possui filhos. Ela vai ocupar a posição de desenvolvedora.  Por último, a Gerente do departamento será Fabiana Raulino. Casada, duas filhas (Maya e Laura).
O salário de todos eles será a média salarial dos departamentos de administração e finanças.

R: Adicionando cargos:

Programador(a):

INSERT INTO ocupacoes(ocupacao_id,ocupacao_title,min_salario,max_salario) VALUES (20,'Programador(a)',4000.00,10000.00);

Gerente:
INSERT INTO ocupacoes(ocupacao_id,ocupacao_title,min_salario,max_salario) VALUES (21,'Gerente de inovações',8200.00,16000.00);

Descobrindo o salario :
SELECT ROUND(AVG(salario)) FROM funcionarios WHERE departamento_id = 10 OR departamento_id = 1 

INSERINDO ELES NO DEPARTAMENTO DE INOVAÇÕES:
William: INSERT INTO `funcionarios`(`funcionario_id`, `primeiro_nome`, `sobrenome`, `email`, `telefone`, `dataContratacao`, `ocupacao_id`, `salario`,`departamento_id`) VALUES ('217','William','Ferreira','william.ferreira@momento.org','400.289.2222','2022-06-29',20, 17000,12);

FERNANDA: INSERT INTO `funcionarios`(`funcionario_id`, `primeiro_nome`, `sobrenome`, `email`, `telefone`, `dataContratacao`, `ocupacao_id`, `salario`, `departamento_id`) VALUES ('218','Fernanda','Lima','fernanda.lima@momento.org','400.289.1111','2022-06-29',20, 17000,12);

Gerente: INSERT INTO `funcionarios`(`funcionario_id`, `primeiro_nome`, `sobrenome`, `email`, `telefone`, `dataContratacao`, `ocupacao_id`, `salario`, `departamento_id`) VALUES ('219','Fabiana','Raulino','fabiana.raulino@momento.org','400.289.3333','2022-06-29',21, 17000,12);

Dependentes:
INSERT INTO dependentes(primeiro_nome,sobrenome,parentesco,funcionario_id) VALUES ('Inara ','Ferreira','Cônjuge',217);

INSERT INTO dependentes(primeiro_nome,sobrenome,parentesco,funcionario_id) VALUES ('Gabriel ','Ferreira','Filho',217);

INSERT INTO dependentes(primeiro_nome,sobrenome,parentesco,funcionario_id) VALUES ('Rodrigo ','Lima','Cônjuge',218);

INSERT INTO dependentes(primeiro_nome,sobrenome,parentesco,funcionario_id) VALUES ('Maya','Raulino','Filho(a)', 219);

INSERT INTO dependentes(primeiro_nome,sobrenome,parentesco,funcionario_id) VALUES ('Laura','Raulino','Filho(a)', 219);

##
9 - Informe todas as regiões em que a empresa atua acompanhadas de seus países.

R: SELECT paises.pais_name AS Pais, regiao.regiao_name FROM paises INNER JOIN regiao WHERE paises.regiao_id = regiao.regiao_id;
##

Filho de quem?

10 - Joe Sciarra é filho de quem?*

R: Ismael Sciarra;

Primeiro se acha qual o id do pai

SELECT * FROM `dependentes` WHERE primeiro_nome ='Joe';

id funcionario, ou seja, do pai 111

SELECT * FROM `funcionarios` WHERE funcionario_id =111;
##

11- Jose Manuel possui filhos?

R: Jose Manuel não possui filhos

SELECT funcionarios.primeiro_nome, dependentes.primeiro_nome FROM dependentes INNER JOIN funcionarios WHERE dependentes.funcionario_id = funcionarios.funcionario_id AND dependentes.sobrenome LIKE '%Manuel%';
##

12 - Qual região possui mais países?

R: Região da Europa, com 25 países

SELECT regiao.regiao_name, COUNT(paises.regiao_id) FROM paises INNER JOIN regiao WHERE regiao.regiao_id = paises.regiao_id;
##

13 - Exiba o nome cada funcionário acompanhado de seus dependentes.

R: SELECT funcionarios.primeiro_nome, funcionarios.sobrenome, dependentes.primeiro_nome, dependentes.sobrenome FROM funcionarios INNER JOIN dependentes WHERE funcionarios.funcionario_id = dependentes.funcionario_id; 
##

14 - Karen Partners possui um cônjuge?

R: Sim, Alec Partners;

SELECT dependentes.primeiro_nome, dependentes.sobrenome from dependentes INNER JOIN funcionarios WHERE funcionarios.funcionario_id = dependentes.funcionario_id AND funcionarios.primeiro_nome LIKE '%Karen%' AND funcionarios.sobrenome LIKE '%Partners%';

##

15 - O ID da tabela de países não segue um padrão numérico. Na sua visão, qual o impacto disso no desenvolvimento do banco?

R: Não haverá impacto no desenvolvimento do banco, pois o ID atende os requisitos de chave primaria e é identificado pelas siglas dos países, exemplo: 'Argentina', 'AR', 2;
##

16 - Escolha um país para se mudar. Qual seria esse país? Por que escolheria esse país? E o departamento. O que seria? Como seriam seus funcionários?

R: Mudaria para o Canadá, pela imagem de paz que o país e seu povo transmitem, criaria o departamento do diálogo, focado em resolução de conflitos na base do dialogo e da tranquilidade, para isso os funcionários seriam pessoas empáticas, calmas e que sabem lidar com conflitos.

##
17 - Atualize as informações na tabela para que seu departamento seja criado.*

R: 
INSERT INTO posicao (endereco, cidade, pais_id) VALUES ('Calgary', 'Canada', 'CA');

INSERT INTO departamento (departamento_name, posicao_id) VALUES('Departamento do dialogo',5401);

