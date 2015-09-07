## Full Stack Fest Review

### Overview

Last week, I attended [Full Stack Fest](http://fullstackfest.com/) in beautiful Barcelona. Full Stack Fest is actually two seperate conferences -- Baruco (Barcelona Ruby Conf), and Future JS -- with a day of workshops in between. There were also 4 nights of sponsored meetups/parties where I got the chance to mingle with international Rubyists and Javascripters.

Disclaimer: this was my first multi-day conference <sup id="a1">[1](#f1)</sup>, so I don't have a lot of conference experience off of which to base my opinions. It seemed like most attendees agreed though when I say FSF was superbly-organized.

Note: this is not a complete list of all the talks given at FSF.

### Baruco

#####Davy Stevenson - "Orders of Magnitude" - [@davystevenson](https://twitter.com/davystevenson)
- Our brains are not good with big and small numbers. As web developers we have to work in the world of trillionths and trillions so we need to rely on tools instead of our intuition when calculating probabilities. 


#####Brian Lilies - "Running Ruby Apps" - [@bryanl](https://twitter.com/bryanl)
- Treating your servers like cattle instead of pets allows you to know for sure what your app is doing. Use new servers each time you deploy so you know that the environment looks exactly the same as the artifact created during the build.


#####Aaron Patterson - "Request and Response" - [@tenderlove](https://twitter.com/tenderlove)
- Rack Middleware: when you send a request in Rails, before hitting the router it must go through copious layers of middleware, which can result in too much computation only to return a 404. Perhaps the router should not be burried in middleware.
- We should eliminate Middleware and encourage competition, or different types of Middleware for different purposes.
- In Spain, it's 'el OL' #lol


#####Aaron Quint - "Beyond JSON: Improving inter-app communication"  - [@aq](https://twitter.com/aq)
[Slides](https://speakerdeck.com/aq/beyond-json-improving-inter-app-communication)
- JSON is easy at first... but as apps get more complex it can become a 'bag of glass'<sup id="a2">[2](#f2)</sup>.
![Alt bag of glass](http://assets.podomatic.net/ts/24/94/ff/eriknovak00/285%3E_8220534.jpg?1420722724)
- Protocol Buffers are worth checking out
-- Handles change well without versioning, using nique tags
-- Explicit types defined in a schema, including nested types
-- Can specify required vs optional fields
- Quint created a simple protocal and client server for request/response TCP Server in go (TCPEZ)[https://github.com/paperlesspost/tcpez]
- To Read: Google's Dapper Paper: (Building a distributed system without introspectability is a fools errand)[http://research.google.com/pubs/pub36356.html]


#####Sandi Metz - "Nothing is Something" - [@sandimetz](https://twitter.com/sandimetz)
Here's a video of this same talk given at RailsConf 2015:
[![Nothing is Something at RailsConf 2015](http://img.youtube.com/vi/29MAL8pJImQ/0.jpg)](https://www.youtube.com/watch?v=29MAL8pJImQ)
- 'if' is an enabler. We should substitute a smarter object instead of checking for nil
- An object does still have to contain a conditional sometimes, but it should be in the right place.
- Inject the players. Use dependency injection. Run from inheritance because it will usually spiral out of control.
- I should probably learn [Smalltalk](https://en.wikipedia.org/wiki/Smalltalk)


#####Ernie Miller - "How to build a skyscraper" - [@erniemiller](https://twitter.com/erniemiller)
[Slides](https://speakerdeck.com/erniemiller/how-to-build-a-skyscraper)
- We can learn lessons about how to craft software well from unexpected places: such as skyscraper building (see slides)


#####Piotr Solnica - "Blending Functional and OO Programming in Ruby" - [@_solnic_](https://twitter.com/_solnic_)
[Slides](https://speakerdeck.com/solnic/blending-functional-and-oo-programming-in-ruby)
- Prefer stateless Objects and use injection dependency
- Get rid of mutable objects. Once you instantiate something, it must be 'ready' because you can't change it later on.
- Objects should only have one single public method (e.g. #call(input))
- Single responsibility principle leads to objects that are like functions


#####John Cinnamond - "Extreme Objected-Oriented Ruby" - [@jcinnamond](https://twitter.com/jcinnamond)
Super cool talk inspired by Sandi Metz's talk where she declared that 'if' is not necessary. Throughout the talk, John built up purely OO numbers. 
His code ended up looking something like this:
```ruby
One.+(One).==(Two)
```
He then created some [challenges](https://github.com/jcinnamond/oo-ruby) to try out.



### Future JS

#####Rachel Andrew - "The Business of Front End Development" - [@rachelandrew](https://twitter.com/rachelandrew)
[Slides](https://speakerdeck.com/rachelandrew/the-business-of-front-end-development)
[Links and Further Reading](https://rachelandrew.co.uk/presentations/business-of-front-end?utm_content=buffer9dcc0&utm_medium=social&utm_source=twitter.com&utm_campaign=buffer)
- Learn and teach the basics first: HTML, CSS, and JavaScript. The rest is just workflow.
-- *Don't become an expert in one brand of hammer. Become a master carpenter. Develop timeless skills*
-- Don't listen to, or worse, become and evangelist for a tool. Having an understanding of the core tools helps you make a better decision.
-- You don't know if the noisy developers are working on a project similar to yours. Understand the whole story.
- We're becoming good at making simple things very complicated (through the use of libraries and frameworks).
- As a community, we should pay attention to web standards and spec development. By learning frameworks, we are masking the issues instead of working to solve them. Get frustrated! Push for better solutions!
- Prioritize the users' experience over your ease of development <sup id="a3">[3](#f3)</sup>
- Progressive Enhancement for the win <sup id="a4">[4](#f4)</sup>
-- *"a robust site or application in the more traditional sense minimizes its dependencies. The minimum dependency for a web site should be an Internet connection and the ability to parse HTML"*<sup id="a5">[5](#f5)</sup>
-- What is the minimum that I need to ship? How can i ensure that minimum protects the core experience for everyone?
-- Never say 'oh yeah, accessibility is *coming*'

#####Massimiliano Mantione - "Transducers FTW!" - [@M_a_s_s_i](https://twitter.com/M_a_s_s_i)
[Slides](http://massimiliano-mantione.github.io/talks/FutureJs2015Transducers/GHP/index.html#/)
Really good explanation of what a transducer is and how to use them. Check out the slides.

#####Nick Heiner - "Procedural Content in JS" - [@nickheiner](https://twitter.com/nickheiner)
[Slides](https://onedrive.live.com/view.aspx?resid=C175B9B686F66FD!138013&ithint=file%2cpptx&app=PowerPoint&authkey=!AAAHyDZV_VELntg)
- There are a lot of different ways to generate content: Midpoint Displacement Algorithm, Iterative subdivision, Markov Chains, Perlin Noise, Simplex Noise, Voronoi Noise, L-Systems/Grammar-based modeling
- npm has tools to generate these `npm install perlin simplex-noise voronoi l-system markoff`
- Lessons learned from generating a map of a city using these tools:
-- Use a seedable randomness source<sup id="a6">[6](#f6)</sup> so you can: use automated testing and reproduce results using the same seed
-- Log Everything
-- Configure Everything - good parameters are important
-- Use the appropriate algorithm. If you use a big subdivided square for the main grid system, it's hard to create diagonal lines.
- Check out the list of references at the end of the slides

#####Steven Wittens - "The Pixel Factory" - [@unconed](https://twitter.com/unconed)
[Slides](http://acko.net/files/gltalks/pixelfactory/online.html#0)
This was the most visually-appealing talk of the conference for me. I strongly recommend just taking a look at the slides since the talk was extremely mathematical, and Wittens' passion is using 3D graphics to explain complex math as it applies to rendering graphics.
- Checkout [MathBox](https://github.com/unconed/MathBox.js), library for making math diagrams in WebGL
- We can simulate warped space with graphics using differential geometry (so cool!) : `f(x, y, z, time, intensity) -> (x, y, z)`
- [three.js](http://threejs.org/): JavaScript 3D library, used by Mathbox




 <b id="f1" > 1 </b> I attended [Goruco](http://goruco.com/), a one day Ruby conference in New York City, earlier this summer. [↩](#a1)
 <b id="f2" > 2 </b> Just stick a bunch of stuff into this hash without thinking about it then when you want to pull something out it's like a bag of glass. [↩](#a2)
 <b id="f3" > 3 </b> [Who Should Pay?](https://www.aaron-gustafson.com/notebook/who-should-pay/) [↩](#a3)
 <b id="f4" > 4 </b> [The Practical Case for Progressive Enhancement](http://sixtwothree.org/posts/the-practical-case-for-progressive-enhancement) [↩](#a4)
 <b id="f5" > 5 </b> [BBC Future Media Standards and Guidelines](http://www.bbc.co.uk/guidelines/futuremedia/accessibility/html/progressive-enhancement.shtml) [↩](#a5)
 <b id="f6" > 6 </b> In this case, Heiner used [alea node model](https://github.com/coverslide/node-alea) [↩](#a6)

