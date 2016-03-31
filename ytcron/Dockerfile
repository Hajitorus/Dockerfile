FROM alpine:3.3
MAINTAINER docker.c@nsuckmyballs.com

ADD get-subs /etc/periodic/15min/get-subs
RUN chmod 0755 /etc/periodic/15min/get-subs
RUN apk update \
	&& apk add ca-certificates zsh youtube-dl \
	&& rm -rf /var/cache/apk/*
CMD /etc/periodic/15min/get-subs
