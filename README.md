# Rails-Docker

Initial setup to start fast your Rails applications
- Ruby 2.5.3
- Postgres 10.9

## Getting started

Clone repo:
```
$ git clone https://github.com/douglara/rails-docker.git
```
Build containers
```
$ cd rails-docker && docker-compose build
```
Install Rails and start new project
```
$ docker-compose run app bash -c "gem install rails; rails new . --database=postgresql"
```
Change ownership of app files for you and re build app container
```
$ sudo chown $USER:$USER -R app && docker-compose build
```

Change you database.yml default connection to:
```
default: &default
  adapter: postgresql
  encoding: unicode
  # For details on connection pooling, see Rails configuration guide
  # http://guides.rubyonrails.org/configuring.html#database-pooling
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
  user: <%= ENV['DB_USER'] %>
  password: <%= ENV['DB_PASSWORD'] %>
  host: <%= ENV['DB_SERVER'] %>
```

Create database table
```
$ docker-compose run app bash -c "rails db:create db:migrate"
```
Start application
```
$ docker-compose up
```



Contributing / Problems?
If you have encountered any problem, difficulty or bug, please start by opening a issue.

Bug reports and pull requests are welcome on GitHub at https://github.com/douglara/rails-docker. This project is intended to be a safe, welcoming space for collaboration.

License
The project is available as open source under the terms of the MIT License.
