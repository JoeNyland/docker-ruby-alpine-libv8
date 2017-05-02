FROM ruby:2.4-alpine
ENV LIBV8_VERSION 3.16.14.16
RUN apk add --update --no-cache libstdc++ && \
    apk add --update --no-cache --virtual build-deps build-base make python git bash && \
    gem install libv8 -v ${LIBV8_VERSION} && \
    gem install therubyracer && \
    apk del build-deps
