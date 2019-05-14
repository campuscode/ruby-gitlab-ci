FROM ruby:2.6
MAINTAINER Campus Code <dev@campuscode.com.br>

ENV NODE_VERSION 8
RUN curl -sL https://deb.nodesource.com/setup_$NODE_VERSION.x | bash -
RUN wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add - \
    && echo "deb http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google.list


RUN apt-get update -qq
RUN apt-get install -y --no-install-recommends nodejs \
      locales google-chrome-stable

RUN echo "en_US.UTF-8 UTF-8" > /etc/locale.gen
RUN locale-gen
ENV LC_ALL en_US.utf8

RUN gem install bundler-audit
