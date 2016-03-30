FROM alpine:edge
MAINTAINER docker.c@nsuckmyballs.com

ADD get-subs /etc/periodic/hourly/get-subs
RUN chmod 0755 /etc/periodic/hourly/get-subs
RUN touch /var/log/ytcron.log
RUN touch /var/log/cron.log

RUN apk update \
	&& apk add ca-certificates zsh \
	&& apk add youtube-dl \
	&& rm -rf /var/cache/apk/*

# I think Alpine is using community by default now?
# --update-cache --repository http://dl-cdn.alpinelinux.org/alpine/edge/community/ \

VOLUME ["/base"]
# ENTRYPOINT ["crond"]
CMD crond && tail -f /var/log/ytcron.log

# DSM's log viewer is useless; we'll monitor logs some other way.
# tail -f /var/log/ytcron.log
