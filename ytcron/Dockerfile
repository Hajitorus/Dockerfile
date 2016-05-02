FROM alpine:3.3
MAINTAINER docker.c@nsuckmyballs.com

ADD get-subs /etc/periodic/15min/get-subs
RUN chmod 0755 /etc/periodic/15min/get-subs
RUN apk update \
	&& apk add ca-certificates coreutils fish youtube-dl \
	&& rm -rf /var/cache/apk/*
CMD crond -f && tail -f /var/log/cron.log
