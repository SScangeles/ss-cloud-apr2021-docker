FROM ubuntu as stage0
RUN apt -y update && \
    apt -y install git && \
    cd /home && git clone https://github.com/SSOrphans/boss-user-service.git && \
    cd boss-user-service && git switch features/SSOR-50-Forgot_Password && \
    cd boss-core && git submodule update --init

FROM maven as stage1
COPY --from=stage0 /home/boss-user-service /home/boss-user-service
RUN cd /home/boss-user-service && mvn -q clean package

FROM openjdk as stage2
COPY --from=stage1 /home/boss-user-service /home/boss-user-service
CMD java -jar /home/boss-user-service/boss-user/target/boss-user-0.0.1-SNAPSHOT.jar