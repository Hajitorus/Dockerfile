FROM alpine:edge
MAINTAINER docker.c@nsuckmyballs.com

ADD get-subs /etc/periodic/hourly/get-subs
RUN chmod 0755 /etc/periodic/hourly/get-subs
RUN apk update \
	&& apk add ca-certificates coreutils fish youtube-dl \
	&& rm -rf /var/cache/apk/*
CMD crond -f && tail -f /var/log/cron.log
