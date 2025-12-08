#If we don't mention any tag it will take latest by default
FROM nginx
LABEL "Project"="Vprofile"
LABEL "Author"="Padma"

RUN rm -rf /etc/nginx/conf.d/default.conf #to remove the default configuration
COPY nginxvproapp.conf /etc/nginx/conf.d/vproapp.conf
