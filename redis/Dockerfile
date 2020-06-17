from alpine:3.11

# Create redis User and Group
RUN addgroup -S -g 1000 redis && adduser -S -G redis -u 999 redis

RUN apk add --no-cache \
	'su-exec>=0.2' \
	tzdata

RUN set -eux \
	wget -D redis.tar.gz "${REDIS_VERSION_URL}"; \
	mkdir -p /var/usr/redis/ \
	tar -xzf redis.tar.gz -C /var/usr/redis --strip-components=1 \
	rm -rf redis.tar.gz \
	export BUILD_TLS=yes \
	make -C /var/usr/redis -j "${inproc}" all; \
	make -C /var/usr/redis install	
