# Based on:
# - https://github.com/nextcloud/fulltextsearch/wiki/Basic-Installation
#   Basic Installation
# - https://stackoverflow.com/questions/42889241/how-to-increase-vm-max-map-count
#   max virtual memory areas vm.max_map_count [65530] is too low, increase to at least [262144]
#   must be configured on docker host
# - Version 6.8.1 is the only one working...
FROM elasticsearch:6.8.1

RUN bin/elasticsearch-plugin install --batch ingest-attachment
