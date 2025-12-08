FROM mysql:8.0.33
LABEL "Project"="Vprofile"
LABEL "Author"="Padma"

#from src/main/resources/application.properties
ENV MYSQL_ROOT_PASSWORD="admin123"
ENV MYSQL_DATABASE="accounts"

#In Docker mysql image offical documentation, it's written that any file ends with .sql or .sh will be executed if you keep those files in docker-entrypoint-intitdb.d folder 
ADD db_backup.sql docker-entrypoint-intitdb.d/db_backup.sql

