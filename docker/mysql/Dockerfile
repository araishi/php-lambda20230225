# FROM mysql:5.7 # m1が動かないので
#FROM --platform=linux/amd64 mysql:8-debian
#FROM --platform=linux/x86_64 mysql:8-debian
#FROM --platform=linux/x86_64 mysql:5.7-debian
#FROM arm64v8/mariadb:latest

FROM arm64v8/mysql:8.0.30

ENV LANG ja_JP.UTF-8
ENV LANGUAGE ja_JP:ja
ENV TZ Asia/Tokyo

COPY mysqld.cnf /etc/mysql/mysql.conf.d/mysqld.cnf
