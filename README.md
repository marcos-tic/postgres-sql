![Alt text](https://raw.githubusercontent.com/marcos-tic/postgres-sql/master/postgresql-logo.png " ")



# postgres-sql

https://www.postgresql.org/        teste

Debian 10

PostgreSQL Apt Repositorio

Se a versão incluída na sua versão do Debian não é a que você deseja, você pode usar o Repositório PostgreSQL Apt. Este repositório se integrará aos seus sistemas normais e gerenciamento de patches e fornecerá atualizações automáticas para todas as versões suportadas do PostgreSQL durante toda a vida útil do PostgreSQL.

The PostgreSQL apt repository supports the currently supported stable versions of Debian:

    Buster (10.x)
    Stretch (9.x)
    Jessie (8.x)

nas seguintes arquiteturas:

    amd64
    i386
    ppc64el

Para usar o repositório apt, siga estas etapas:

    Criar o arquivo /etc/apt/sources.list.d/pgdg.list, and add a line for the repository:

         deb http://apt.postgresql.org/pub/repos/apt/ buster-pgdg main

    Importe a chave de assinatura do repositório e atualize as listas de pacotes:

         wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
         sudo apt-get update

Para mais informações sobre o repositório do apt, incluindo respostas a perguntas frequentes, consulte a página do apt no wiki.
Incluído na distribuição

O Debian inclue o PostgreSQL por padrão. Para instalar o PostgreSQL no Debian, use o comando apt-get (ou outro gerenciador de pacotes):

  apt-get install postgresql-11

O repositório contém muitos pacotes diferentes, incluindo complementos de terceiros. Os pacotes mais comuns e importantes são (substitua o número da versão conforme necessário):
postgresql-client-11 	client libraries and client binaries
postgresql-11 	core database server
postgresql-contrib-9.x 	additional supplied modules (part of the postgresql-xx package in version 10 and later)
libpq-dev 	libraries and headers for C language frontend development
postgresql-server-dev-11 	libraries and headers for C language backend development
pgadmin4 	pgAdmin 4 graphical administration utility

# Setar a senha do usuário postgres do SO
passwd postgres

Acessar o Postgres
# su - postgres
~$ psql



dependecia
sudo apt-get update
sudo apt-get install gnupg



Visit the PostgreSQL Ubuntu download site:
https://www.postgresql.org/download/linux/ubuntu/

First check PostgreSQL Verison Available in Ubuntu
apt show postgresql

Install PostgreSQL from Ubuntu repositories

Updating
Step1 :- sudo apt update

Installation
Step2 :- sudo apt install postgresql postgresql-contrib

Verify
sudo -u postgres psql -c "SELECT version();"

Login into Useraccount
Postgres Account or Login
Step4 :- sudo -i -u postgres
Step4 :- sudo su - postgres

Exit
Step5 :- \q

Login into Database
Without Switching Accounts
Step6 :- sudo -u postgres psql

Exit
Step7 :- \q

Creating New PostgreSQL Role

Inside the Postgres
Step8 :- createuser --interactive
OR
Outside the Postgres
Step9 :- sudo -u postgres createuser --interactive
OR
Step9 :- sudo su - postgres -c "createuser itcloudnet"

For More Information
man createuser

Creating New PostgreSQL Database

Inside Postgres
Step10 :- createdb itcloudnet
OR
Outside Postgres
Step11 :- sudo -u postgres createdb itcloudnet
OR
Step11 :- sudo su - postgres -c "createdb itcloudnetdb"

Grant Permission
Step12 :- sudo -u postgres psql
Step13 :- grant all privileges on database itcloudnetdb to itcloudnet;

Opening with New Role
Step12 :- sudo adduser itcloudnet

New Database Connect
Step13 :- sudo -i -u itcloudnet 
OR
Step13 :- sudo -u itcloudnet psql
Step14 :- psql

To Connect Different Database
Step15 :- psql -d postgres

To Check Connection Information
Step16 :- \conninfo

Creating and Deleting Tables
Step17 :- CREATE TABLE cloudnetwork (
    equip_id serial PRIMARY KEY,
    type varchar (50) NOT NULL,
    color varchar (25) NOT NULL,
    location varchar(25) check (location in ('north', 'south', 'west', 'east', 'northeast', 'southeast', 'southwest', 'northwest')),
    install_date date
);

Output with Sequence
Step18 :- \d

Without Sequence
Step19 :- \dt

Adding, Querying and Deleting Data in Table
Step20 :-
INSERT INTO cloudnetwork (type, color, location, install_date) VALUES ('slide', 'blue', 'south', '2020-04-20');
INSERT INTO cloudnetwork (type, color, location, install_date) VALUES ('swing', 'yellow', 'northwest', '2019-08-16');


Step21 :- SELECT * FROM cloudnetwork;

Step22 :- DELETE FROM cloudnetwork WHERE type = 'slide';


Adding and Deleting Columns from a Table
Step23 :- ALTER TABLE cloudnetwork ADD last_maint date;

Step24 :- SELECT * FROM cloudnetwork;

Step25 :- ALTER TABLE cloudnetwork DROP last_maint;

Updating Data in a Table
Step26 :- UPDATE cloudnetwork SET color = 'red' WHERE type = 'swing';

Step27 :- SELECT * FROM cloudnetwork;

TO RESET PASSWORD
ALTER USER postgres WITH PASSWORD 'itcloudnet$123!';

Enable remote access to PostgreSQL server
sudo nano /etc/postgresql/10/main/postgresql.conf
listen_addresses = '*'

sudo service postgresql restart
ss -nlt | grep 5432

sudo nano /etc/postgresql/10/main/pg_hba.conf
i case of 10 it can be 11 version
Replace with peer ---> md5
sudo service postgresql restart

