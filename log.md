# 100 Days Of Code - Log

### Day 0: May 16, 2018

**Today's Progress**: Created the beginnings of GoREST, a RESTful app I'm using to learn how to write Go...and REST apps.

**Thoughts:** I spent an inordinate amount of time developing a project frameworks for building and shipping the app in Docker contianers.  I didn't count this toward the hour, but it took longer than I thought it would.  Luckily it's re-usable for other projects.

I ran into some issue with variable assignment.  I kept getting syntax errors expecting "{" after assigning a variable.  I am not sure *how* I fixed it.  I think *maybe* the word "interface" is a reserved word?  Or maybe I just changed enough that when I switched it to "iface" everything worked.   All this to just print a message about what interface I'm listening on...

I want to start writing tests from the begining here, but I'm unsure how to do that with the app I've written so far. I've read how tests work in Go, so I get the idea, but how do you test a REST api?

**Link to work:** [GoREST](https://github.com/clcollins/gorest)

### Day 1: May 17, 2018


**Today's Progress**: Got some basic tests working for the HTTP requests, got logging working to STDOUT, as container culture dictates.

**Thoughts:** I need to read more about Go types, and how to identify them.  Over and over, I was trying to print or return types that were not convertable or whatever.

It's stupid annoying trying to get *http.Request info, or I have not yet figured out how to do it well.

**Link to work:** [GoREST](https://github.com/clcollins/gorest)

### Day 2: May 19, 2018

**Today's Progress**: Figured out how to capture query parameters from the *http.Request using `req.URL.Query()`, and both log them and use them to return data.
 
 I also got a better understanding of what maps are - they're hashes.  They works just like hashes, exactly the same way as hashs work in Ruby and Python.  Why this took so long to realize I 100% attribute to the `map[KeyType]ValueType` notation in the Go docs.

Also learned about variable scope.  That is going to trip me up.  It's a bit different than I'm used to.

Also learned the difference between `Println` and `Printf` in a practical context.

**Thoughts:** A decent amount of troubleshooting and thinking I didn't understand the Go docs turned out to be a failed understanding of how to pass query parameters using HTTPie.  (Hint: `cheese==american` is correct.  `cheese=american` is not.)  I finally confirmed with CURL that I was doing the right thing in the code, but sending bad data with HTTPie.  When I run into a road block in the future it will help to double-check assumpions, especially if I can use another tool to do so. 

**Link to work:** [GoREST](https://github.com/clcollins/gorest)

### Day 3: May 20, 2018

**Today's Progress**:  No real actual progress today, which is frustrating.  I played around with Structs, and tried to understand what I was doing.  Along with that, tried to encode json from a struct, and failed.  Or perhaps succeeded, but was printing something I didn't expect.  I spend the last part of the time trying tweaking some tests.

**Thoughts:** Before the next hour, I need to spend an hour working on a tutorial.  Apparently, there's a "How to Write A Webapp" section to the Golang docs, so I should try to run throught that.

**Link to work:** [GoREST](https://github.com/clcollins/gorest)


### Day 4: May 21, 2018

**Today's Progress**:  Did a bunch of reading & random testing of Structs, trying to learn how they work.

**Thoughts:**

1. I do not understand pointers.  I suspect it's a programming fundimental I didn't ever learn in picking up programming with practical/operational exposure.
2. I am unsure about the is-a vs. has-a nature of embedded type structs, re: [The GoLang Book Intro 9](https://www.golang-book.com/books/intro/9). I can't seem to get them to inherit from the parent.

**Link to work:** 

1. [My GoTour & Related Code](https://github.com/clcollins/gotour)
2. [Trying out inherited\(?\) structs](https://play.golang.org/p/IgfztiWDFyr)

### Day 5: May 22, 2018

**Today's Progress**: Today wrote my own impelmentation of the [RabbitMQ Golang sender example](https://www.rabbitmq.com/tutorials/tutorial-one-go.html), with functions and a few vars.

**Thoughts:**

1. Today felt better.  I was using someone else's code as an example to work from, but relatively easily broke all the bits out into functions so I could get more familiar with them.

2. Had some trouble getting used to declaring return variables, but getting the hang of it.

3. Found two flaws in the RabbitMQ Go example!

**Link to work:** 

1. [GoBunny](https://github.com/clcollins/gobunny)

### Day 6: May 23, 2018

**Today's Progress**: I added a receiver function to the code I wrote yesterday, following the  [RabbitMQ Golang receiver example](https://www.rabbitmq.com/tutorials/tutorial-one-go.html), and added a parser for command line arguments so whether or not the binary sends or receives is determined via the command line arguments

**Thoughts:**

1. I cannot, for some reason, get the actual message to parse from the "send" sub-command, so every send message is the default.  Will look closer tomorrow.
2. RabbitMQ is slick.  I already knew this, but it reinforces it.
3. I sort of get pointers.  I know how they work, but not really maybe *why* or the underlying idea of it.

**Link to work:** 

1. [GoBunny](https://github.com/clcollins/gobunny)

### Day 7-8: May 26, 2018

**Today's Progress**: I missed days 7 and 8 due to injury, so I did two hours of coding today to make it up, and will do two hours tomorrow to cover today's and tomorrow's code.

Today, I didn't make a ton of progress, but I did dive in a bit to learn more about the `flags` package, correcting some assumptions I had and writing a test program to verify how it works.  I also learned how to reference environment variables in Go, so that the GoBunny RabbitMQ clients I've been working on can set the server to connect via env var, as is a normal way in the Docker world.  Finally, I fixed some errors in the Docker Compose and README.md documentation.

**Thoughts:**

1. Now that I understand the flags command better, I see how it works.  I want to say it's not as easy as Python's Argparse, but, really, Argparse is stupid and complicated; I just know it.

2. It's harder to troubleshoot go code.  Writing out a dummy program, or leaving in bad code while you try to test just doesn't work.  I am pretty sure that's because it has to compile.  If I'd ever had to write C in college, I think I would be more used to it.  This does highlight one of the benefits of interpreted languages.


**Link to work:** 

1. [GoBunny](https://github.com/clcollins/gobunny)
2. [My GoTour & Related Code](https://github.com/clcollins/gotour): specifically `flag.go`


### Day 9-10: May 28, 2018

**Today's Progress**: I did another two hours today to make up for another missed day.  Two more hours tomorrow, and I'll be back on track.

Today, I moved away from the RabbitMQ client in Go, as at this point it was more of an exercise in how RabbitMQ worked, and less about how Go works.  I started down trying to learn to open a connection to a MySQL database, and to interact with said DB.  I took the opportunity to learn a bit about how to unmarshal YAML to a struct, and use the values of the struct to create a DSN.  I then used the DSN to open a connection to a remote MySQL database and check that the connection is there.

**Thoughts:**

1. I got very, very little done over the course of two hours.  I can see why some languages value having frameworks to do all of this for you.
2. I think I have the hang of structs now, and how to use them.  I created one to store the credentials read from a YAML file, and another to format data going into the MySQL database.  That bit is starting to fall into place for me.


**Link to work:** 

1. [GoDB](https://github.com/clcollins/godb)

### Day 11-12: May 29, 2018

**Today's Progress**: Another two hours of code in one day, finally catching up from missing a few days.

Not productive in terms of output of new code, but I had several a-ha moments where the lightbulb came on.  I think I made a lot of _mental_ progress, even if I didn't make any _written_ progress.

**Thoughts:**

_Constants:_

Somehow I got into this and didn't learn or think about constants, but that's a big part of some of the things I do - some hard-coded configuration info set at the top of the file, unlikely to be changed, but good to have, just in case.  I can go back and change all those `var host string = 'localhost'`, heh.

_Astaxie must be a Dwarf Fortress player:_

`err := errors.New("emit macho dwarf: elf header corrupted")`

Instantly a fan.  Though, everyone should be, anyway.  The ["Build web application with Golang"](https://astaxie.gitbooks.io/build-web-application-with-golang/content/en/02.2.html) post of his/hers is one of the best introductions to Go for beginners that I've found.

[Astaxie on Github](https://github.com/astaxie)

_Maps!!:_

"map behaves like a dictionary in Python. Use the form map[keyType]valueType to define it." - The aforementioned Astaxie

SON OF A CRAP FOR CRAP - how has *this* eluded me?  No one stated it in so many terms and I was so confused by the format explanations elsewhere - `map[keyType]valueType` -  that I didn't pick up on it.  FINALLY, I get it.  I feel stupid though.  I should have figured that out.

_The For control statement, and it's expressons:_

This also eluded me for a bit.  ...for "some var" ; "some conditional" ; "somevar"...  Cool.

**Link to work:** 
2. [My GoTour & Related Code](https://github.com/clcollins/gotour): specifically `maps.go`
