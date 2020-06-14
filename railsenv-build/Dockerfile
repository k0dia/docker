# Bring the ruby
FROM ruby:2.5
# Update apt-get and install required packages
RUN apt-get update && apt-get install -y \
    build-essential \
    libpq-dev \
    nodejs \
    postgresql-client \
    yarn
# Change working directory to /product-register
WORKDIR /product-register
# Bring Gemfile and Gemfifle.lock to /product-register/ from build context
COPY Gemfile Gemfile.lock /product-register/
# install rails
RUN bundle install