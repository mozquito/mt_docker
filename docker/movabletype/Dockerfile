FROM perl:5.30.1
WORKDIR /usr/src

RUN apt-get update
RUN apt-get install libjpeg-dev libpng-dev -y
# MovableTypeのスクリプト内のShebangが/usr/bin/perlなので合わせる
RUN ln -sf /usr/local/bin/perl /usr/bin/perl

RUN cpanm Net::Server \
&& cpanm XMLRPC::Transport::HTTP \
&& cpanm LWP::Protocol::https \
&& cpanm DBI DBD::mysql \
&& cpanm Cache::Memcached::Fast \
&& cpanm Task::Plack \
&& cpanm XMLRPC::Transport::HTTP::Plack \
&& cpanm Net::Server::SS::PreFork \
&& cpanm JSON::XS \
&& cpanm Imager \
&& cpanm Amazon::S3::Thin
COPY ./mt /var/www/mt
COPY ./docker-mt-entrypoint /usr/local/bin/
WORKDIR /var/www/mt
ENTRYPOINT ["docker-mt-entrypoint"]
EXPOSE 5000
