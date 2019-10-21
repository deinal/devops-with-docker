FROM ruby:2.6.0
RUN git clone https://github.com/docker-hy/rails-example-project.git
WORKDIR rails-example-project
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash - \
    && apt install -y nodejs
RUN bundle install
RUN rails db:migrate
EXPOSE 3000
CMD rails s
