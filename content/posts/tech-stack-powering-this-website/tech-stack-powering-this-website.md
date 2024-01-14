---
title: "The tech stack powering this website"
date: 2024-01-14
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
The tech stack powering this website

Hey there! If you know me through my side job related to building websites, you might assume this website is built with WordPress. But nope! On my journey to becoming a writer, I wanted to learn something new (WordPress had become too easy for me) and experience the magical feeling that comes with learning and creating something new.

To be honest, my hacker mind initially thought, "Let's build a blog from scratch using an esoteric programming language, create a solid framework, release it as open source to the public, and finally, build the blog on top of it." From another perspective I also considered some great options that focus on the writing experience, such as Bearblog, Substack, and Medium. 

After swinging between extremes, from the "full developer experience" to the "full writer experience," it was time to find equilibrium between both and choose the best way to create a blog. So, I started exploring popular stacks and frameworks available.

Among the many stacks available (like MEAN, MEARN, LAMP, Django, Ruby on Rails, LAMP), I wanted to choose something "powerful." This was clearly a subjective matter so I made a list of characteristics I wanted on my website (big-picture requirements, if they can be termed as such):

* A blog
* An "about me" page
* A minimalistic view
* Social media icons
* Built-in support for multilingual pages
* Fast loading pages
* Mobile responsiveness
* Easy maintenance and scalability
* A custom domain
* No need to pay for hosting

It's clear that what I had in mind was simple (just static content, no databases, no fancy backend). So, why would I want to use a "powerful" stack? It would be over engineering! I can easily create a simple project using HTML and CSS (or even use a pure HTML, CSS template), and that's it!

This brings up an interesting point. If you are an engineer/maker/developer, you might agree that we became engineers/makers/developers because we enjoy building things and solving complex problems. Sometimes, it's exciting to imagine a complex solution to a problem pursuing the “ultimate solution to all cases related to it”.

However, besides I'm skeptical that  an “ultimate solution to all cases” exists for a problem,  it is really common to see people getting lost in the problem, losing focus on other important parameters, such as time available, feasibility, and complexity… and paradoxically that creates a more important a problem because you disconnect from the impactful solution and the outcomes of the thing you work on. 

Creating and delivering something can become an interesting or a Sisyphean activity. At the end you as a maker/creator must find fulfillment in the act of shipping stable iterations of your creation over time in the same way you find it in the act of solving complex issues. 

So, I had finally made some progress… I had decided to create my blog with pure HTML, CSS and JS. But I was not happy with that choice. While the decision to use pure HTML, CSS, and JS is commendable for the full customization it provides, incorporating a framework could be a better idea and a strategic choice to overcome common development hurdles related with time of developing, group the complexity involved, improve efficiency, and enhance the overall performance of your blog website as it evolves.

So, I spent almost two weeks (in my free time) reading all over the web about frameworks until I found an architectural approach called "Jamstack" (JavaScript, APIs, Markdown) which I liked. In layman terms it simplifies the development workflow by decoupling the front-end from the back-end, precompiling/prerendering much of the content before the HTML reaches the browser, creating clean and atomic deployments, serving a website/application statically on the edge.

For my plans it seems to provide an interesting mix of authoring & developer experience. To start writing all you have to do is create a new markdown file in the proper directory and start writing and if you are in developer mode you can add your own customizations to the website. 

Once you are done, you have the capability to deploy the website directly from a Git repository in order to share it with the world.  Hosting a static site is versatile and often quite affordable, as it can be accommodated on various platforms. As we exclusively deal with purely static files, we sidestep the typical deployment limitations associated with hosting dynamic server-side languages along with a database server.

This approach is not new; to be honest the idea to decouple the presentation layer from the business logic already existed. But Jamstack is basically a way of rebranding old-known static sites, saying that you should generate the pages you are serving and push them to a CDN edge network for Time to First Byte (TTFB speed). The goal is to eliminate time spent on a server while the visitor waits for the frontend to load.

Besides this static approach may look simple, they also offer a lot of flexibility. You can still make your website dynamic by using API calls to anything that needs to access a DBno matter if you are following a serverless or serverful approach. So, jamstack doesn't mean exclusively “static content”... It's a way of showing people in web development that we should be doing more things statically when we can, and separating out dynamic components into their own APIs. In this way, we improve the performance, the UX (User Experience) of the application, and of course, the SEO.

After searching the different SSGs available, I decided to use Hugo. Why Hugo? Well, two important points distinguish Hugo from the majority of other static site generator options. Firstly, it is among the few generators written in the Go programming language and since I learned Go 2 years ago, I wanted to put hands-on practice in a real project (some aspects of building even basic Hugo templates require at least a basic knowledge of the Go language). Secondly, it prioritizes extremely fast build times. This can be a crucial consideration, as build times with other engines may become a significant impediment as the size of a site increases ((it can compile a single web page in milliseconds and an entire website in seconds).

Installing Hugo is mostly a matter of downloading the proper binary executable for your platform from the releases page. Hugo supports Windows, OS X, Linux, and FreeBSD. I’m using Linux Mint on my current laptop so I first installed Homebrew and then I installed Hugo using: brew install hugo.

Once Hugo is installed, it’s time to generate your website. To do that you can create it from scratch using the command “hugo new site [project name]” (which will create your basic folder and files structure and you have to code your own layouts in the “layouts” folder) or you can use a Hugo Theme. In my case I found the theme “love it” which I loved but wanted to customize so I forked it and renamed it to “HateIt” (I wanted to feel rebel :’v).

Is important to notice that Hugo offers the option of specifying the kind of data format you would like to use when generating new files. By default Hugo uses TOML (because of readability and simplicity) but you can use Yaml or even Json files. Also when designing custom layouts for your static site in Hugo, it is common to employ the Go html/template library as this enables users to shape the structure and presentation of their content through the creation of custom templates using Go's templating syntax (current documentation about this is not really friendly to read) but is a nice challenge).

Before continuing it is also important to notice that Hugo manages the basic configuration of your website in the “config.toml” file which takes its template from the file of the same name but in the theme directory. So take a look at that file (if you are using a theme usually all use it) if you want to perform some basic customizations without modifying directly the internal html, css and js files.

So after I had created my Hugo project, added my customized theme "Hate IT" as a Git submodule inside the directory “themes” and configured the “config.toml” file, I tried a dummy entry… and it worked! (Hugo also includes a local web server to test your site locally), so the next step was to host it so everybody could access my website.

There are a lot of options available to host your Jamstack website for free. Of course you can pay for a hosting service but why would you do that when there are free options available and with really good offers in SLA uptimes! I considered two options: Netlify and Github Pages. I decided to use  “Github pages” because I like GitHub :D

I pushed my Hugo website repository to GitHub (though I hadn't mentioned it earlier, I've been using Git since I created my Hugo website, hehe). It's important to note that this repository must be named "[username].github.io"(because GitHub rules). Then I set up a GitHub action to deploy it every time I pushed a new change, and voila, my website was live! Of course, later on, I connected a custom domain because I wasn't a fan of using the lengthy free URL that GitHub provided.

I truly hope you enjoyed this post! If it was helpful to you, I'm pleased. Please consider sharing it with others or quoting it if, someday, you use content from these words. Happy hacking juakers!
