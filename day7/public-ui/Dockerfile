FROM ubuntu as stage0
RUN apt -y update && \
    apt -y install git && \
    cd /home && git clone https://github.com/SSOrphans/boss-public-ui.git && \
    cd boss-public-ui && git switch demo/ecs-test

FROM node
COPY --from=stage0 /home/boss-public-ui /home/boss-public-ui
RUN npm install -g @angular/cli && cd /home/boss-public-ui && npm install
CMD cd /home/boss-public-ui && ng serve --host 0.0.0.0 --port 4200