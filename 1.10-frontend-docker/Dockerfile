FROM ubuntu:18.04

WORKDIR /frontend-app

# Install programs necessary for the setup.
RUN apt-get update && apt-get install -y zip curl apt-utils build-essential wget && \ 
# Get project files from github.
    wget https://github.com/docker-hy/frontend-example-docker/archive/master.zip && \
    unzip master.zip && \
    rm master.zip && \
    chmod +x frontend-example-docker-master && \
# Install node. 
    cd frontend-example-docker-master && \ 
    curl -sL https://deb.nodesource.com/setup_10.x | bash - && \
    apt-get install -y nodejs && \
    node -v && npm -v && \ 
# Build and run the project. 
    npm install && \ 
    npm run build && \
    npm install -g serve 

# Container should be run with port 5000 published, e.g. docker run -p 5000:0000 mycontainer. 
EXPOSE 5000 

CMD serve -s -l 5000 frontend-example-docker-master/dist
