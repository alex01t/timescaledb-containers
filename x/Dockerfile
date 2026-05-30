FROM ghcr.io/cloudnative-pg/postgresql:18.4

USER root

RUN apt update && apt-get install -y \
  wget curl ca-certificates gnupg apt-transport-https lsb-release \
  vim procps net-tools dnsutils

RUN echo "deb https://packagecloud.io/timescale/timescaledb/debian/ $(lsb_release -c -s) main" |  tee /etc/apt/sources.list.d/timescaledb.list
RUN wget --quiet -O - https://packagecloud.io/timescale/timescaledb/gpgkey | gpg --dearmor -o /etc/apt/trusted.gpg.d/timescaledb.gpg

RUN apt update && apt install -y timescaledb-2-postgresql-18 postgresql-client-18


USER 26

