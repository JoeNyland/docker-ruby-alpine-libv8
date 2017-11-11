FROM ruby:2.4-alpine
RUN apk add --update --no-cache --virtual build-deps build-base python git bash && \
    gem install libv8 -v 3.16.14.16 && \
    gem install therubyracer && \
    apk del build-deps
