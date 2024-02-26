## SQL Docker
If you need to configure mysql, you need to follow step by step:
1. cd `.docker/config/my.cof`
- Define your configuration
2. In `.docker/Dockerfile`
- add `COPY ./my/config/my.conf /etc/mysql/conf.d/my.conf`
3. Run `docker compose up -d --build`
a
