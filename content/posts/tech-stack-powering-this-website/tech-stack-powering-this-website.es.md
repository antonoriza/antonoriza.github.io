---
title: "El stack tecnológico de este website"
date: 2023-12-22
draft: false
toc:
  enable: false
  auto: false
linkToMarkdown: false
share:
      enable : true
      Twitter : true
      HackerNews : true
      Reddit : true
      Whatsapp : true
      Facebook: False
      Line : false
      Weibo : false
---
Hey, if you know me through my side job related to building websites, you may think this website is built with WordPress... but nope! To be honest, I considered it as an option, but on my journey to becoming a writer, I wanted to try and learn something new (WordPress has become really easy), and feel the weird and magical emotion that debugging and fixing bugs brings.

Between a lot of stacks available (like MEAN, MEARN, LAMP, Django, Ruby on Rails, LAMP) I wanted to choose something “new” and “powerful”… But what is the definition of “powerful”? For my purpose this was clearly a subjective matter based on my needs… so I needed to understand what I wanted in my website, so I made a list of things that I wanted in my website:

I want:
* A blog
* An “about me” page.
* A minimalistic view.
* Social media icons.
* Build in support for multilingual pages.
* Fast loading pages.
* Mobile responsive.
* Easy to maintain and scale.
* A custom domain.
* Don't want to pay for hosting.


Is clear that what I had in mind looked simple. My hacker mind was like “lets build all from scratch using an esoteric programming language, creating a solid framework and then releasing it as open source to the public”... but then I was like “Am I gonna code or am I gonna write?” 

I considered some really good alternative options that focus on the writing experience like Bearblog, Substack and Medium… but using them was boring in the end, at least for my initial motivations. If you don't want to deal with technical stuff take a look at those platforms, they are really good!

So, I spent almost two weeks (in my free time) searching all over the web until I found an architectural approach called “Jamstack” (Javascript, APIS, Markdown) which I loved. After reading about it, it simplifies the development workflow decoupling the front-end from the back-end by precompiling/prerendering  as much of the content before the HTML reaches the browser creating clean, atomic deployments serving a website/application statically on the edge.

At the end it provides an interesting mix of authoring & developer experience… from a big view all you have to do is create a new markdown file in the proper directory and start writing… Once you are done you have the capability to deploy the website directly from a git repository. 
This approach is not new, tbh the idea to decouple the presentation layer from the business logic already existed but JAMstack is basically a way of rebranding old known static sites saying that you should generate the pages you are serving and push them to a CDN edge network for Time to first byte (TTFB speed) (the goal is to eliminate time spent on a server while the visitor waits for the frontend to load), but you can still make them dynamic by using API calls to anything that needs to access a DB following a serverless or serverful approach. It's a way of showing people that we should be doing more things statically when we can, and separating out dynamic components into their own APIs. In this way we improve the performance, the UX (User Experience) of the application and of course the SEO.

After searching the different SSGs available I decided to use Hugo. Why Hugo? Well it is written in Go and since I learned Go 2 years ago I wanted to put hands on practice in a real project. Also it is really fast (it can compile a single web page in milliseconds and an entire website in seconds). ANother point that really influenced my choice is a template that I found called “Loved it” which was exactly what I had in mind.

So what steps did I follow? Well I forked the template on my GitHub account, made some customizations and called it “Hate it” (yeah I know the name is not really creative but is what I had in mind at the moment). After that I had everything so I created a Hugo project, added the template “Hate IT” as a git submodule, tried a dummy entry and it worked! Well, “worked” locally (on my computer) so the next step was to host it so everybody could access my website. I pushed my Hugo website into a new github repository and wrapped up a github action to deploy it every time I push a new change.