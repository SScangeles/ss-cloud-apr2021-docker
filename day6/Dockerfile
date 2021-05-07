FROM ubuntu as stage0
RUN apt -y update && \
    apt -y install git && \
    cd /home && \
    git clone https://github.com/SSOrphans/boss-core.git

FROM maven as stage1
COPY --from=stage0 /home/boss-core /home/boss-core
RUN cd /home/boss-core && mvn clean package