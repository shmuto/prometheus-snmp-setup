FROM golang:latest

RUN apt-get update && \
    apt-get install -y libsnmp-dev unzip curl&& \
    go install github.com/prometheus/snmp_exporter/generator@latest &&\
    curl -fsSL https://raw.githubusercontent.com/prometheus/snmp_exporter/main/generator/Makefile -o /opt/Makefile


WORKDIR "/opt"

ENTRYPOINT ["/bin/bash"]

ENV MIBDIRS mibs

CMD ["make mibs"]