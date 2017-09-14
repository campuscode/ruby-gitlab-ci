FROM buildpack-deps:jessie

RUN apt-get update -qq
RUN apt-get install vim mysql-client cron -y --force-yes --no-install-recommends
RUN wget https://cache.ruby-lang.org/pub/ruby/1.8/ruby-1.8.7-p374.tar.gz
RUN tar -zxvf ruby-1.8.7-p374.tar.gz

WORKDIR ruby-1.8.7-p374
RUN ./configure
RUN make
RUN make install

RUN wget https://rubygems.org/rubygems/rubygems-2.6.13.tgz
RUN tar -xvzf rubygems-2.6.13.tgz
WORKDIR rubygems-2.6.13
RUN ruby setup.rb

RUN echo 'gem: --no-ri --no-rdoc --no-document' > ~/.gemrc

WORKDIR /system

RUN gem update --system 1.8.30
