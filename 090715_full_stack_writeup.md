## Full Stack Fest Review

### Overview

Last week, I attended [Full Stack Fest](http://fullstackfest.com/) in beautiful Barcelona. Full Stack Fest is actually two seperate conferences -- Baruco (Barcelona Ruby Conf), and Future JS -- with a day of workshops in between. There were also 4 nights of sponsored meetups/parties where I got the chance to mingle with international Rubyists and Javascripters.

Disclaimer: this was my first multi-day conference <sup id="a1">[1](#f1)</sup>, so I don't have a lot of conference experience off of which to base my opinions. It seemed like most attendees agreed though when I say FSF was superbly-organized.

### Baruco

####Davy Stevenson - "Orders of Magnitude"
[@davystevenson](https://twitter.com/davystevenson)
- Our brains are not good with big and small numbers. As web developers we have to work in the world of trillionths and trillions so we need to rely on tools instead of our intuition when calculating probabilities. 

####Brian Lilies - "Running Ruby Apps"
[@bryanl](https://twitter.com/bryanl)
- Treating your servers like cattle instead of pets allows you to know for sure what your app is doing. Use new servers each time you deploy so you know that the environment looks exactly the same as the artifact created during the build.

####Aaron Patterson - "Request and Response"
[@tenderlove](https://twitter.com/tenderlove)
- Rack Middleware: when you send a request in Rails, before hitting the router it must go through copious layers of middleware, which can result in too much computation only to return a 404. Perhaps the router should not be burried in middleware.
- We should eliminate Middleware and encourage competition, or different types of Middleware for different purposes.
- In Spain, it's 'el OL' #lol

####Aaron Quint - "Beyond JSON: Improving inter-app communication" 
[@aq](https://twitter.com/aq) | [Slides!](https://speakerdeck.com/aq/beyond-json-improving-inter-app-communication)
- JSON is easy at first... but as apps get more complex it can become a 'bag of glass'<sup id="aq">[aq](#aq2)</sup>.
![Alt bag of glass](http://assets.podomatic.net/ts/24/94/ff/eriknovak00/285%3E_8220534.jpg?1420722724)
- Protocol Buffers are worth checking out
-- Handles change well without versioning, using nique tags
-- Explicit types defined in a schema, including nested types
-- Can specify required vs optional fields
- Quint created a simple protocal and client server for request/response TCP Server in go (TCPEZ)[https://github.com/paperlesspost/tcpez]
- To Read: Google's Dapper Paper: (Building a distributed system without introspectability is a fools errand)[http://research.google.com/pubs/pub36356.html]

####Sandi Metz - "Nothing is Something"
[@sandimetz](https://twitter.com/sandimetz)
Here's a video of this same talk given at RailsConf 2015:
[![Nothing is Something at RailsConf 2015](http://img.youtube.com/vi/29MAL8pJImQ/0.jpg)](https://www.youtube.com/watch?v=29MAL8pJImQ)
- 'if' is an enabler. We should substitute a smarter object instead of checking for nil
- An object does still have to contain a conditional sometimes, but it should be in the right place.
- Inject the players. Use dependency injection. Run from inheritance because it will usually spiral out of control.
- I should probably learn (Smalltalk)[https://en.wikipedia.org/wiki/Smalltalk]

####Ernie Miller - "How to build a skyscraper"
[@erniemiller](https://twitter.com/erniemiller) | [Slides!](https://speakerdeck.com/erniemiller/how-to-build-a-skyscraper)
- We can learn lessons about how to craft software well from unexpected places: such as skyscraper building (see slides)

####Piotr Solnica - "Blending Functional and OO Programming in Ruby"
[@_solnic_](https://twitter.com/_solnic_) | [Slides!](https://speakerdeck.com/solnic/blending-functional-and-oo-programming-in-ruby)
- Prefer stateless Objects and use injection dependency
- Get rid of mutable objects. Once you instantiate something, it must be 'ready' because you can't change it later on.
- Objects should only have one single public method (e.g. #call(input))
- Single responsibility principle leads to objects that are like functions

####John Cinnamond - "Extreme Objected-Oriented Ruby"
[@jcinnamond](https://twitter.com/jcinnamond)
Super cool talk inspired by Sandi Metz's talk where she declared that 'if' is not necessary. Throughout the talk, John built up purely OO numbers. 
His code ended up looking something like this:
```ruby
One.+(One).==(Two)
```
He then created some [challenges](https://github.com/jcinnamond/oo-ruby) to try out.



### Future JS


 <b id="f1" > 1 </b> I attended [Goruco](http://goruco.com/), a one day Ruby conference in New York City, earlier this summer. [↩](#a1)
 <b id="aq2" > 1 </b> Just stick a bunch of stuff into this hash without thinking about it then when you want to pull something out it's like a bag of glass. [↩](#aq)

