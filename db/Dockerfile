FROM postgres:14.1-alpine
# specifying source image

#Adding files to initialize the DB with some data
COPY 01-CreateScheme.sql  /docker-entrypoint-initdb.d/01-CreateScheme.sql
COPY 02-InsertData.sql  /docker-entrypoint-initdb.d/02-InsertData.sql
