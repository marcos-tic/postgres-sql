# postgres-sql


PostgreSQL Apt Repository

If the version included in your version of Debian is not the one you want, you can use the PostgreSQL Apt Repository. This repository will integrate with your normal systems and patch management, and provide automatic updates for all supported versions of PostgreSQL throughout the support lifetime of PostgreSQL.

The PostgreSQL apt repository supports the currently supported stable versions of Debian:

    Buster (10.x)
    Stretch (9.x)
    Jessie (8.x)

on the following architectures:

    amd64
    i386
    ppc64el

To use the apt repository, follow these steps:

    Create the file /etc/apt/sources.list.d/pgdg.list, and add a line for the repository:

         deb http://apt.postgresql.org/pub/repos/apt/ buster-pgdg main

    Import the repository signing key, and update the package lists:

         wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
         sudo apt-get update

For more information about the apt repository, including answers to frequent questions, please see the apt page on the wiki.
Included in distribution

Debian includes PostgreSQL by default. To install PostgreSQL on Debian, use the apt-get (or other apt-driving) command:

  apt-get install postgresql-11

The repository contains many different packages including third party addons. The most common and important packages are (substitute the version number as required):
postgresql-client-11 	client libraries and client binaries
postgresql-11 	core database server
postgresql-contrib-9.x 	additional supplied modules (part of the postgresql-xx package in version 10 and later)
libpq-dev 	libraries and headers for C language frontend development
postgresql-server-dev-11 	libraries and headers for C language backend development
pgadmin4 	pgAdmin 4 graphical administration utility

# Setar a senha do usuário postgres do SO
passwd postgres






