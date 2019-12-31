FROM ruby:2.6.0
RUN apt-get update && apt-get install -y nodejs
COPY . .
RUN bundle update --bundler
RUN bundle install
ENV RAILS_ENV production
ENV SECRET_KEY_BASE secret
RUN rails db:migrate
RUN rake assets:precompile
CMD ["rails", "s", "-e", "production"]
EXPOSE 3000
