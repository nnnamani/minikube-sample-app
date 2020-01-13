FROM ruby:2.7.0

WORKDIR /app
ADD . $WORKDIR

RUN bundle install

CMD bundle exec ruby app.rb -e production
