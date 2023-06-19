FROM httpd:2.4.57-alpine
#using small source image for proxy

COPY  ./public-html/ /usr/local/apache2/htdocs/
COPY ./httpd.conf /usr/local/apache2/conf/httpd.conf
#copying proxy configuration files 
