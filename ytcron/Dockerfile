FROM alpine:edge
MAINTAINER docker.c@nsuckmyballs.com

ADD get-subs /etc/periodic/hourly/get-subs
RUN chmod 0755 /etc/periodic/hourly/get-subs
RUN touch /var/log/ytcron.log
RUN touch /var/log/cron.log

RUN apk update \
	&& apk add ca-certificates ffmpeg zsh youtube-dl \
	&& rm -rf /var/cache/apk/*

# Run the command on container startup
CMD crond && tail -f /var/log/ytcron.log

# First attempt. Hope it works?
