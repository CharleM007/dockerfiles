FROM alpine:latest
MAINTAINER Philipp Garbe <philipp.garbe@web.de>

# alias rake='docker run -it --rm -v $(pwd):/root/rake --log-driver none pgarbe/rake "$@"'

RUN apk update && apk add \
	build-base \
	ca-certificates \
	ruby-dev \
	&& rm -rf /var/cache/apk/* \
  gem install bundler

ENV HOME /root
WORKDIR $HOME/rake

ENTRYPOINT [ "rake" ]
