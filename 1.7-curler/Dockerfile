FROM ubuntu:16.04

# install curl as a layer
RUN apt-get update && apt-get install -y curl

WORKDIR /
 
RUN touch curl-website.sh && echo 'echo "Input website:";read website; echo "Searching.."; sleep  1; curl http://$website;' >> curl-website.sh

RUN chmod +x curl-website.sh

CMD ["/bin/bash", "./curl-website.sh"]  

