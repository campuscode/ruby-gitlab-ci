FROM ruby:3.1.2
LABEL author="Campus Code <dev@campuscode.com.br>"

ENV NODE_VERSION 18
RUN curl -sL https://deb.nodesource.com/setup_$NODE_VERSION.x | bash -

RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - \
    && echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list

RUN apt-get update -qq
RUN apt-get install -y --no-install-recommends nodejs \
      locales \
      firefox-esr \
      chromium \
      yarn

RUN echo "en_US.UTF-8 UTF-8" > /etc/locale.gen
RUN locale-gen
ENV LC_ALL en_US.utf8

RUN gem install bundler-audit
