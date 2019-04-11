## Ruby on Rails Helloworld Project

1. Create blog application, use PostgreSQL as database
  ```shell
  $ rails new blog -d postgresql
  ```
2. Switch to the directory
  ```shell
  $ cd blog
  ```
3. Configuring a PostgreSQL Database
  - If you choose to use PostgreSQL, your config/database.yml will be customized to use PostgreSQL databases
  - Change the username and password in the development section as appropriate
  ```
  development:
  adapter: postgresql
  encoding: unicode
  database: blog_development
  pool: 5
  username: blog
  password:
  ```
4. Creating the Database
  ```shell
  $ rake db:create
  ```
5. Create at Minimum A Controller and A View
  ```shell
  $ rails generate controller home index
  ```
6. Rails will create several files for you, including app/views/home/index.html.erb. This is the template that will be used to display the results of the index action (method) in the home controller. Open this file in your text editor and edit it to contain a single line of code
  ```html
  <h1>Hello, Rails!</h1>
  ```
7. Start Server
  ```shell
  $ rails server
  ```
  
