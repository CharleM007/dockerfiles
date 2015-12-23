FROM alpine:latest
MAINTAINER Philipp Garbe <philipp.garbe@web.de>

# alias rake='docker run -it --rm -v $(pwd):/root/bundle \
#                        -e AWS_REGION=$AWS_REGION \
#                        -e AWS_ACCESS_KEY_ID=$AWS_ACCESS_KEY_ID \
#                        -e AWS_SECRET_ACCESS_KEY=$AWS_SECRET_ACCESS_KEY \
#                        -e AWS_SESSION_TOKEN=$AWS_SESSION_TOKEN \
#                        --log-driver none \
#                        pgarbe/bundle "$@"'

RUN apk update && apk add \
	build-base \
	ca-certificates \
	ruby-dev \
	&& rm -rf /var/cache/apk/*

RUN gem install bundler

ENV HOME /root
WORKDIR $HOME/bundle

ENTRYPOINT [ "bundle" ]
