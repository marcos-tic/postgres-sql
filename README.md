# postgres-sql


yum -y install https://download.postgresql.org/pub/repos/yum/reporpms/EL-7-x86_64/pgdg-redhat-repo-latest.noarch.rpm 
yum -y install epel-release yum-utils 
yum-config-manager --enable pgdg12
yum install postgresql12-server postgresql12 postgresql12-contrib 
mkdir -p /trd0/postgres/data 
chown -Rf postgres:postgres /trd0/postgres 
chmod 755 /trd0
chmod -Rf 770 /trd0/postgres
visudo 

        postgres        ALL=NOPASSWD:/bin/systemctl stop postgresql-12,/bin/systemctl start postgresql-12, /bin/systemctl restart postgresql-12, /bin/systemctl status postgresql-12

vim /etc/profile 
       
	    export PATH=$PATH:/bin:/usr/pgsql-12/bin
	    export PGDATA=/trd0/postgres/data

source /etc/profile


yum install postgresql12-devel postgresql12-contrib libcurl-devel postgis25_12* gcc gcc-c++ make proj49* geos37* spatial4j libxml2* gdal* gtk3* SFCGAL* CUnit* libxslt* dblatex* ogr_fdw12 ogr_fdw12-debuginfo pgagent_12 pgagent_12-debuginfo unzip clang llvm7.0* centos-release-scl-rh llvm-toolset-7-llvm devtoolset-7 llvm5.0 llvm-toolset-7* mailx --skip-broken

wget https://github.com/pramsey/pgsql-http/archive/master.zip 
unzip master.zip
cd pgsql-http-master/ 
make
make install 

/bin/sh /usr/lib64/pgsql/pgxs/src/makefiles/../../config/install-sh -c -m 644 ./http--1.3.sql ./http--1.2--1.3.sql ./http--1.1--1.2.sql ./http--1.0--1.1.sql  '/usr/pgsql-12/share/extension'

cp http.control /usr/pgsql-12/share/extension/ 

mv /var/lib/pgsql/12/data /var/lib/pgsql/12/data-dist 

ln -s /trd0/postgres/data /var/lib/pgsql/12/data


systemctl enable postgresql-12
/usr/pgsql-12/bin/postgresql-12-setup initdb
systemctl start postgresql-12 


Digitar o comando ifconfig e verificar o IP interno e incluir no arquivo abaixo 

vim /trd0/postgres/data/postgresql.conf 
       listen_addresses = 'IP LAN SERVIDOR' 

systemctl restart  postgresql-12

# Setar a senha do usuário postgres do SO
passwd postgres






