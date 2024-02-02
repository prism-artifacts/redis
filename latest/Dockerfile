FROM redislabs/redisgraph:latest as redisgraph
FROM redislabs/redisearch:latest as redisearch

FROM bitnami/redis:latest
COPY --from=redisgraph /usr/lib/redis/modules/redisgraph.so /usr/lib/redis/modules/redisgraph.so
COPY --from=redisearch /usr/lib/redis/modules/redisearch.so /usr/lib/redis/modules/redisearch.so


CMD ["/run.sh", "--loadmodule", "/usr/lib/redis/modules/redisgraph.so", \
                "--loadmodule", "/usr/lib/redis/modules/redisearch.so"]