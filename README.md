# postgres

### connect to 
psql --host=$HOST --user=$USER $DATABASE

### list databases
\l

### connect to database
\c $database

### list schemas
\dn 

### list tables in schemas
\dt $SCHEMA.*


### Postgresql basics
DROP DATABASE $database;
CREATE DATABASE $database;
CREATE USER $user WITH PASSWORD 'myPassword';
GRANT ALL PRIVILEGES ON DATABASE $database TO $user;

### READ ONLY USER FOR POSTGRES
CREATE USER $USER WITH LOGIN PASSWORD 'MyPassword';
GRANT USAGE ON SCHEMA public to $USER;
ALTER DEFAULT PRIVILEGES IN SCHEMA public GRANT SELECT ON TABLES TO $USER;
GRANT CONNECT ON DATABASE $DATABASE TO $USER;
\c $DATABASE
GRANT USAGE ON SCHEMA public TO $USER;
GRANT SELECT, UPDATE ON ALL SEQUENCES IN SCHEMA public TO $USER;
GRANT SELECT, INSERT, UPDATE, DELETE ON ALL TABLES IN SCHEMA public TO $USER;
###
