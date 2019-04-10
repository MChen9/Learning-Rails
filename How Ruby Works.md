## How Ruby Works

1. The Mechanics of Writing a Ruby Program
  - Syntax of Ruby
    ```ruby
    # Getting a line of keyboard input
    gets
    strings = gets # string is a variable
    
    # str to int
    "100".to_i
    
    # Conditional execution
    if x == 7
        # code
    else
        # code
    end
    ```
    
  - Check Syntax Error
    ```ruby
    ruby -cw file.rb
    ```
    
  - `print` vs. `puts`
    *  `print` not add a new line
    * `puts` jump to a new line
    
  - Keyboard and File Input
    * Keyboard
      `gets`

      ```ruby
      print "Hello. Please enter a Celsius value: " 
      c = gets
      f = (c.to_i * 9 / 5) + 32
      print "The Fahrenheit equivalent is "
      print f
      puts "."

      # shorten version
      print "Hello. Please enter a Celsius value: "
      print "The Fahrenheit equivalent is ", gets.to_i * 9 / 5 + 32, 
      ".\n"
      ```
      
    * File
      ```ruby
      num = File.read("temp.dat")
      ```
    * Write File
      ```ruby
      c = gets.to_i
      f = (c * 9 / 5) + 32
      fh = File.new("temp.out", "w")
      fh.puts f # print to the output file
      fh.close
      ```
 
  - Using classes from other files
    * `require_relative`
      * `require`similar to  `import`
      * `require_relative` for files in the same directory
      ```ruby
      # file c2fin.rb
      class CtoFin
        def start(c)
          f = (c * 9 / 5) + 32
          puts "The number is " + c.to_s 
          print "Result: "
          puts f
        end # code block should with _end_
      end

      # file c2fout.rb
      require_relative 'c2fin'
      m = CtoFin.new()
      m.start(34)
      ```

2. Get the Path Where Ruby installed
  ```shell
  irb -rrbconfig
  RbConfig::CONFIG["bindir"]
  ```

3. Change Ruby Version
  ```shell
  $ echo "2.6.1" > .ruby-version
  ```

4. `ERb`
  - If you want some Ruby code executed, enclose it between <% and %>
  - If you want the result of the code execution to be printed out, as part of the output, enclose the code between <%= and %>
    ```ruby
    # save as erbdemo.rb
    <% page_title = "Demonstration of ERb" %> <% salutation = "Dear programmer," %> <html>
    <head>
    <title><%= page_title %></title>
    </head>
    <body>
    <p><%= salutation %></p>
    <p>This is a brief demonstration of how ERb fills out a template.</p> </body>
    </html>
    ```
    ```shell
    $ erb erbdemo.rb
    ```
    output:
    ```
    <html>
    <head>
    <title>Demonstration of ERb</title>
    </head>
    <body>
    <p>Dear programmer,</p>
    <p>This is a brief demonstration of how ERb fills out a template.</p> </body>
    </html>
    ```
      
        
        
    
