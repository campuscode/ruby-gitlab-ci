FROM ruby:2.7.1
MAINTAINER Campus Code <dev@campuscode.com.br>

ENV NODE_VERSION 8
RUN curl -sL https://deb.nodesource.com/setup_$NODE_VERSION.x | bash -
RUN wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add - \
    && echo "deb http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google.list

RUN apt-get update -qq
RUN apt-get install -y --no-install-recommends nodejs \
      locales \
      google-chrome-stable

ENV PHANTOMJS_VERSION 2.1.1
RUN curl -L -O https://bitbucket.org/ariya/phantomjs/downloads/phantomjs-$PHANTOMJS_VERSION-linux-x86_64.tar.bz2
RUN tar -jxvf phantomjs-$PHANTOMJS_VERSION-linux-x86_64.tar.bz2 phantomjs-$PHANTOMJS_VERSION-linux-x86_64/bin/phantomjs
RUN mv phantomjs-$PHANTOMJS_VERSION-linux-x86_64/bin/phantomjs /usr/local/bin/
RUN rm phantomjs-$PHANTOMJS_VERSION-linux-x86_64.tar.bz2 && rm -rf phantomjs-$PHANTOMJS_VERSION-linux-x86_64/bin
RUN chmod 755 /usr/local/bin/phantomjs

RUN echo "en_US.UTF-8 UTF-8" > /etc/locale.gen
RUN locale-gen
ENV LC_ALL en_US.utf8

RUN gem install bundler-audit
