FROM alpine:edge
MAINTAINER docker.c@nsuckmyballs.com

ADD get-subs /etc/periodic/15min/get-subs
RUN chmod 0755 /etc/periodic/15min/get-subs
RUN touch /var/log/cron.log

RUN apk update \
	&& apk add ca-certificates ffmpeg zsh youtube-dl \
	&& rm -rf /var/cache/apk/*

# Run the command on container startup
CMD crond && tail -f /var/log/cron.log

# First attempt. Hope it works?
