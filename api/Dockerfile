FROM ruby:2.6.5-alpine

ENV RUNTIME_PACKAGES="bash tzdata postgresql-dev postgresql" \
    DEV_PACKAGES="build-base curl-dev" \
    LANG="C.UTF-8"

RUN apk update && \
    apk upgrade && \
    apk add --no-cache --update $RUNTIME_PACKAGES && \
    apk add --virtual build-packages --no-cache $DEV_PACKAGES

WORKDIR /api
COPY /api/Gemfile ./
COPY /api/Gemfile.lock ./
RUN bundle install
RUN apk del build-packages
COPY . /api

EXPOSE 3000

CMD ["bundle", "exec", "rails", "server", "-b", "0.0.0.0", "-p", "3000"]
