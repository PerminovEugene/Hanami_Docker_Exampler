FROM ruby:2.3.1
RUN apt-get update && apt-get install -y build-essential libpq-dev nodejs
RUN useradd -ms/bin/bash hanami-user
USER hanami-user
WORKDIR /home/hanami-user/project
ADD ./test_ruby/Gemfile /home/hanami-user/project/Gemfile
ADD ./test_ruby/Gemfile.lock /home/hanami-user/project/Gemfile.lock
USER root
RUN chown hanami-user:hanami-user /home/hanami-user/project/Gemfile.lock
USER hanami-user
RUN bundle install
ADD ./test_ruby /home/hanami-user/project