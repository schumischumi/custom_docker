# Based on:
# - https://github.com/dsteinkopf/elasticsearch-ingest-attachment
#   remove x-pack because of license problems spamming log file with massive amounts of errors
# - https://github.com/nextcloud/fulltextsearch/wiki/Basic-Installation
#   Basic Installation
# - https://stackoverflow.com/questions/42889241/how-to-increase-vm-max-map-count
#   max virtual memory areas vm.max_map_count [65530] is too low, increase to at least [262144]
FROM elasticsearch:6.6.2

RUN bin/elasticsearch-plugin install --batch ingest-attachment

# remove x-pack because of license problems spamming log file with massive amounts of errors
RUN bin/elasticsearch-plugin remove x-pack --purge \
    &&  sed -i 's/^xpack/#xpack/' config/elasticsearch.yml

# fix: max virtual memory areas vm.max_map_count [65530] is too low, increase to at least [262144]
RUN echo "vm.max_map_count=262144" >> /etc/sysctl.conf
