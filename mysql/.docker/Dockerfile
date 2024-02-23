FROM mysql:8.0.36

WORKDIR /mysql

# COPY ./my/config/my.conf /etc/mysql/conf.d/my.conf
RUN ls -l -a ../
COPY . /mysql/myworkspace

RUN rm -rf /mysql/myworkspace/.docker/data
