FROM mongo:latest AS mongosass


RUN mkdir -p /data/sass \
&& chown -R mongodb:mongodb /data/sass


COPY ./SASS.bck /var/backups/SASS.bck
RUN mongod -fork --logpath /var/log/mongodb.log --dbpath /data/sass && mongorestore /var/backups/SASS.bck && mongod --dbpath /data/sass --shutdown

VOLUME /data/sass

CMD mongod --dbpath /data/sass --bind_ip 0.0.0.0
