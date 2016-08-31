FROM elasticsearch:2.3
MAINTAINER Jeff Sheng

# Add ENV
ENV ESW /usr/share/elasticsearch
ENV ESW_BIN $ESW/bin

# Mount config
COPY $PWD/config $ESW/config

# Add plugin --- ik
RUN mkdir $ESW/plugins/ik
COPY $PWD/ik $ESW/plugins/ik

# Add plugin --- kopf 
RUN plugin install lmenezes/elasticsearch-kopf

# Change Workdir
WORKDIR $ESW_BIN

# change user
USER elasticsearch

# Setting port
EXPOSE 9200 9300

# You know , for search.
CMD ["elasticsearch"]