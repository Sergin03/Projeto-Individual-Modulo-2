# Módulo 2 – Sistema RESILIADATA
## Objetivo
O objetivo do projeto é realizar a modelagem (conceitaul e lógico) de um banco de dados da empresa Resilia. 

A Atividade consistem em 4 perguntas sendo:
```
1 - Quais são as entidades necessárias?
```
Empresa_Parceira: Representa as empresas parceiras.

 Funcionario: Representa os colaboradores que trabalham para as empresas parceiras

 Tecnologia:  Representa as tecnologias disponíveis.

 Utiliza: Esta tabela representa a relação entre os funcionários e as tecnologias que eles utilizam.

 Fornece: Representa a relação entre os colaboradores e as tecnologias que eles utilizam
```
2 - Quais são os principais campos e seus respectivos tipos?
```
## Principais Campos e Tipos de Dados:

Empresa_Parceira:
id_empresa (INT): Chave primária autoincrementada.

CNPJ (VARCHAR): Nome da empresa.

telefone (VARCHAR): Número de telefone da empresa.

email (VARCHAR): Endereço de e-mail da empresa.


Funcionario:
id_funcionario (INT): Chave primária autoincrementada.

nome (VARCHAR): Nome do funcionario.

cpf (VARCHAR): cpf do funcionario.

telefone (VARCHAR): telefone do funcionario.

Tecnologia:
id_tecnologia (INT): Chave primária autoincrementada.

nome (VARCHAR): Nome da tecnologia.

area (VARCHAR): Área de aplicação da tecnologia.

descricao (VARCHAR): Descrição da tecnologia (opcional).

id_empresa (INT): Chave estrangeira referenciando a tabela Empresa_Parceira.


Utiliza:

  id_Utiliza SERIAL PRIMARY KEY,  
  id_Tecnologia INT REFERENCES Tecnologia (id_Tecnologia),
  id_funcionario INT REFERENCES funcionario (id_funcionario)

Fornece:

id_Fornece SERIAL PRIMARY KEY,  
id_Tecnologia INT REFERENCES Tecnologia (id_Tecnologia),
id_Empresa_parceira INT REFERENCES Empresa_Parceira (id_Empresa_parceira)

```
3 - Relacionamentos entre as Entidades:
```
A tabela funcionario possui uma chave estrangeira idEmpresa_Parceira que referencia a tabela Empresa_Parceira.
A tabela Utiliza possui duas chaves estrangeiras, id_Tecnologia e id_funcionario, que referenciam as tabelas Tecnologia e funcionario, respectivamente.
A tabela Fornece possui duas chaves estrangeiras, id_Tecnologia e id_Empresa_parceira, que referenciam as tabelas Tecnologia e Empresa_Parceira, respectivamente.
```
4 - Simule 2 registros para cada entidade.
```
## Adicionar registros para Empresa_Parceira

INSERT INTO Empresa_Parceira (nome, telefone, email ) VALUES 
('Empresa A', '123456789', 'empresa_a@example.com'),
('Empresa B', '987654321', 'empresa_b@example.com');

Adicionar registros para Tecnologia
INSERT INTO Tecnologia (nome, descricao, area) VALUES 
('Javascript', 'Linguagem de programação', 'Desenvolvimento de software'),
('Python', 'Linguagem de programação', 'Ciência de dados');

Adicionar registros para Funcionario
INSERT INTO Colaborador (nome, email, cpf, telefone) VALUES 
('Sergio', 'sergio@example.com', 'Desenvolvedor', '123.124.123-55, '12331345'),
('Maria', 'maria_eduarda@example.com', 'Analista de Dados','123.123.213-66, '12431346');

Adicionar registros para Utiliza
INSERT INTO Utiliza (id_empresa, id_tecnologia) VALUES 
(1, 1),
(2, 2);

Adicionar registros para Tecnologia
INSERT INTO Tecnologia (id_funcionario, id_tecnologia) VALUES 
(1, 1),
(2, 2);
