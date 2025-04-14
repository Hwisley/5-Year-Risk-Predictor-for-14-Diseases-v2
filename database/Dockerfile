FROM mcr.microsoft.com/mssql/server:2019-latest

ENV ACCEPT_EULA=Y

ENV DATA_DIR=/mnt/data
ENV SQL_DIR=/mnt/sql
ENV HANSHIN_DB=HealthMIS
ENV SNU_DB=AutocareHCB

USER root

WORKDIR /app

COPY entrypoint.sh /app/entrypoint.sh
RUN chmod +x /app/entrypoint.sh

USER mssql

ENTRYPOINT ["/app/entrypoint.sh"]
