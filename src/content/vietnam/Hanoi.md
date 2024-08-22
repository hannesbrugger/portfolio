---
title: Hanoi
publishDate: 2020-03-02 00:00:00
img: /assets/nfq/hanoi/hanoi.jpeg
description: |
  My final City was Hanoi, the capital of Vietnam
tags:
  - Last step
---

# Hanoi

With the train I've traveld in 17 hours from DaNang to Hanoi, my last city on the list.

#### Multilanguage
All the major design issues are solved and now the last big part should be made, the multilanguage.
As already mentioned is it in general easy to build Astro in more than one language but my requirement was to even translate the url. That means: 
- home/bai-viet/chuyen-doi-so-trong-linh-vuc-thuong-mai
should be translated to:
- en/home/insights/digital-transformation-in-trade

#### Problems
We have to work close with our database, in this case our CMS Prismic. You can provide every type with a additional language. The problem is the changing fetch call. Was it before ok to use
<code>await client.getByUID(type, name)</code>
you now have to use
<code>await client.getByUID(type, name, { lang:Langs[language] } )</code>

- A other problem was how to store the different names of parent pages ?

- And the most big problem: how to keep running the "switch lang" button without JS and how to know the translated url ?

#### Solutions
Unfortunately the first problem has no easy solution. Most of the time I spend in waiting the CMS loading the content so I can change it. And there was a lot to change because:

The solution was to switch all uid's (the ids I call the types with) to full written url's. Problem, no "/" allowed, so there is a function in every linking between content to render the uid to a working url. The solution was to use "__" as "/" and swap it in the code.

So all the types, all the linking and all the fetching had to be changed.

But what about the "switch lang" button now ? 
There for I used a little JS. When we fetch page data to build our routing I also fetch data of any other lang. In this way I'm able to put those url's (uid's) in meta data tags on the page.
the client side JS grabs those tags and renders the coresponding switch-buttons.
In that way we even have the UIX that we can just see button when there is really a content in another language. 

## Office
It is the smalest of all offices. It is also part of a coworking space and located in a tower on the higher flors.
You rarely see more than 5 people in this office, what supports more close contacts among the people.
And sometimes you can even hear people play guitar.

<p align="center">
  <img src="/assets/nfq/hanoi/IMG_8961.jpeg" width="350" title="hover text">
  <img src="/assets/nfq/hanoi/IMG_05CE9D690ADE-1.jpeg" width="350" alt="accessibility text">
</p>


## City
It is the capital of Vietnam and you can feel it on the bussy streets. But you can see a lot in the old town, like the train street or the Hoan-Kiem lake. You also have to try the famose egg coffe !
There are many little or big lakes where people work out in the evening. It is a nice place for just watching people passing by.

<p align="center">
  <img src="/assets/nfq/hanoi/IMG_6A7D56FAF32C-1.jpeg" width="350" title="hover text">
  <img src="/assets/nfq/hanoi/IMG_516C1B3CEC7A-1.jpeg" width="350" alt="accessibility text">
</p>
<p align="center">
  <img src="/assets/nfq/hanoi/IMG_2E45FD9BCF51-1.jpeg" width="350" title="hover text">
  <img src="/assets/nfq/hanoi/IMG_CF9B9A3678F7-1.jpeg" width="350" alt="accessibility text">
</p>