FROM ruby:2.4
MAINTAINER Campus Code <dev@campuscode.com.br>

ENV NODE_VERSION 7
RUN curl -sL https://deb.nodesource.com/setup_$NODE_VERSION.x | bash -
RUN apt-get update -qq
RUN apt-get install -y --no-install-recommends nodejs

ENV PHANTOMJS_VERSION 2.1.1
RUN curl -L -O https://bitbucket.org/ariya/phantomjs/downloads/phantomjs-$PHANTOMJS_VERSION-linux-x86_64.tar.bz2
RUN tar -jxvf phantomjs-$PHANTOMJS_VERSION-linux-x86_64.tar.bz2 phantomjs-$PHANTOMJS_VERSION-linux-x86_64/bin/phantomjs
RUN mv phantomjs-$PHANTOMJS_VERSION-linux-x86_64/bin/phantomjs /usr/local/bin/
RUN rm phantomjs-$PHANTOMJS_VERSION-linux-x86_64.tar.bz2 && rm -rf phantomjs-$PHANTOMJS_VERSION-linux-x86_64/bin
RUN chmod 755 /usr/local/bin/phantomjs

RUN gem install bundler-audit
