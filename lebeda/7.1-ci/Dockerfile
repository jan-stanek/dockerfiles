FROM jstanek/lebeda:7.1

MAINTAINER Jan Stanek <jan.stanek@skaut.cz>

RUN apt-get update

RUN apt-get install -y bzip2 build-essential chrpath libssl-dev libxft-dev \
 libfreetype6 libfreetype6-dev libfontconfig1 libfontconfig1-dev

RUN curl -s https://packagecloud.io/install/repositories/github/git-lfs/script.deb.sh | bash && apt-get install git-lfs && git lfs install

ENV PHANTOM_JS phantomjs-1.9.8-linux-x86_64

RUN curl -L https://bitbucket.org/ariya/phantomjs/downloads/$PHANTOM_JS.tar.bz2 | tar xjf - -C /usr/local/share \
    && ln -sf /usr/local/share/$PHANTOM_JS/bin/phantomjs /usr/local/bin

RUN pecl install xdebug && docker-php-ext-enable xdebug
