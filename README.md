![Alt text](https://raw.githubusercontent.com/marcos-tic/postgres-sql/master/postgresql-logo.png " ")



# postgres-sql

https://www.postgresql.org/

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

