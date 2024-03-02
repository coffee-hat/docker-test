FROM ruby:alpine
RUN apk add --update build-base curl
RUN gem install rackup
RUN gem install sinatra
ADD hasher.rb /
CMD ["ruby", "hasher.rb"]
EXPOSE 80
HEALTHCHECK \
  --interval=1s --timeout=2s --retries=3 --start-period=1s \
  CMD curl http://localhost/ || exit 1
