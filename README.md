# Rails-Docker

Basic Rails 2.5.3 clean setup with postgres 10.9 to start development project fast.


## Getting started

Clone repo:
```
$ git clone https://github.com/douglara/rails-docker.git
```
Build containers
```
$ cd rails-docker && docker-compose build
```
Install Rails
```
$ docker-compose run app gem install rails 
```
Start new project
```
$ docker-compose run app rails new app
```

Create database table
```
$ rails db:create db:migrate
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