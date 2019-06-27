FROM memcached:latest
# MAINTAINER liushuaicai<liushuaicai@100tal.com>

# Port to expose (default: 11211) 
EXPOSE 11211 

# Set the user to run Memcached daemon 
# USER daemon 

# Set the entrypoint to memcached binary 
ENTRYPOINT memcached 

# Default Memcached run command arguments 
CMD ["-m", "64"]
