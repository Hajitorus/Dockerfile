FROM alpine:edge
MAINTAINER docker.c@nsuckmyballs.com

ADD get-subs /etc/periodic/hourly/get-subs
RUN chmod 0755 /etc/periodic/hourly/get-subs
RUN touch /var/log/ytcron.log
RUN touch /var/log/cron.log

RUN apk update \
	&& apk add ca-certificates ffmpeg zsh \
	&& apk add youtube-dl --update-cache --repository http://dl-4.alpinelinux.org/alpine/edge/community/ \
	&& rm -rf /var/cache/apk/*

# Run the command on container startup
# CMD crond && tail -f /var/log/ytcron.log
CMD crond -f
