# 100 Days Of Code - Log

### Day 0: May 16th, 2018

**Today's Progress**: Created the beginnings of GoREST, a RESTful app I'm using to learn how to write Go...and REST apps.

**Thoughts:** I spent an inordinate amount of time developing a project frameworks for building and shipping the app in Docker contianers.  I didn't count this toward the hour, but it took longer than I thought it would.  Luckily it's re-usable for other projects.

I ran into some issue with variable assignment.  I kept getting syntax errors expecting "{" after assigning a variable.  I am not sure *how* I fixed it.  I think *maybe* the word "interface" is a reserved word?  Or maybe I just changed enough that when I switched it to "iface" everything worked.   All this to just print a message about what interface I'm listening on...

I want to start writing tests from the begining here, but I'm unsure how to do that with the app I've written so far. I've read how tests work in Go, so I get the idea, but how do you test a REST api?

**Link to work:** [GoREST](https://github.com/clcollins/gorest)

### Day 1: May 17th, 2018


**Today's Progress**: Got some basic tests working for the HTTP requests, got logging working to STDOUT, as container culture dictates.

**Thoughts:** I need to read more about Go types, and how to identify them.  Over and over, I was trying to print or return types that were not convertable or whatever.

It's stupid annoying trying to get *http.Request info, or I have not yet figured out how to do it well.

**Link to work:** [GoREST](https://github.com/clcollins/gorest)

### Day 2: May 19th, 2018


**Today's Progress**: Figured out how to capture query parameters from the *http.Request using `req.URL.Query()`, and both log them and use them to return data.
 
 I also got a better understanding of what maps are - they're hashes.  They works just like hashes, exactly the same way as hashs work in Ruby and Python.  Why this took so long to realize I 100% attribute to the `map[KeyType]ValueType` notation in the Go docs.

Also learned about variable scope.  That is going to trip me up.  It's a bit different than I'm used to.

Also learned the difference between `Println` and `Printf` in a practical context.

**Thoughts:** A decent amount of troubleshooting and thinking I didn't understand the Go docs turned out to be a failed understanding of how to pass query parameters using HTTPie.  (Hint: `cheese==american` is correct.  `cheese=american` is not.)  I finally confirmed with CURL that I was doing the right thing in the code, but sending bad data with HTTPie.  When I run into a road block in the future it will help to double-check assumpions, especially if I can use another tool to do so. 

**Link to work:** [GoREST](https://github.com/clcollins/gorest)

