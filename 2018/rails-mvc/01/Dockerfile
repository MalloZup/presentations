FROM ruby:2.3.1
# rails  and whenever cron
RUN apt-get update -qq && apt-get install -y build-essential libpq-dev nodejs cron sqlite3 rake
RUN mkdir /dogpark
WORKDIR /dogpark
COPY Gemfile /dogpark/Gemfile
RUN bundle install
COPY . /dogpark
# expose rails
EXPOSE 3000
# initialize database and run server
CMD cd /dogpark/dogpark/ && bundle exec rails server -b 0.0.0.0
