---
layout: post
title: 'Minimalist footer example'
date: 2018-04-07
excerpt: "I love the minimalist look and Raleway is awesome at giving me just that!."
tags: [sample post, code, highlighting]
comments: true
---

Below you'll find some code snipits for a footer I built that I really connected with. I was trying for something with a sleek, minimalist feel. I didn't want too much content; just the necessities: a simple call-to-action and some recognizable links. I wanted a thin font and I really liked the look of slim, white lines against a dark grey background. Enjoy!

## HTML

#### Raleway is an open-sourced Google font. I chose to use font-weight: 100

{% highlight html %}
{% raw %}
<head>
  <link href='https://fonts.googleapis.com/css?family=Raleway:100' rel='stylesheet' type='text/css'>
</head>
{% endraw %}
{% endhighlight %}

#### Just a simple unordered list. The icons I used are downloaded images from ionicons.com. This is another open source resource where you can download a pack of common icons as png documents.

{%highlight html %}
{% raw %}
<footer>
  <div class="footer-wrapper">
    <h2 class="follow-me">Follow Me</h2>
    <ul class="social-links">
      <li><a href="#"><img src="img/social-facebook-outline.png" alt=""/></a></li>
      <li><a href="#"><img src="img/social-github-outline.png" alt=""/></a></li>
      <li><a href="#"><img src="img/social-instagram-outline.png" alt=""/></a></li>
      <li><a href="#"><img src="img/social-linkedin-outline.png" alt=""/></a></li>
      <li><a href="#"><img src="img/social-twitter-outline.png" alt=""/></a></li>
    </ul>
  </div>
</footer>
{% endraw %}
{% endhighlight %}

## CSS

#### Important things to note:
  * The padding: 6% in the footer rule allows the h2 and unordered list to sit in the middle of the element.
  I could have used relative and absolute positioning for this but I think this is simpler and more responsive.
  * Changing the display of the h2, ul (.social-links) and li elements to inline allows them to sit next to each other.
  This is an essential aspect of the styling because h2, ul and li elements are block-level elements and will default
  to be on top of one another if you don't specify.

{% highlight css %}
footer {
  background-color: #202020;
  clear: both;
  padding: 6%;
}
.footer-wrapper {
  width: 45%;
  margin: 0 auto;
}
.social-links {
  display: inline;
}
footer h2 {
  font-family: 'Raleway';
  font-weight: 100;
  display: inline;
  padding: 0;
  color: #fff;
  font-size: 1.25em;
}
footer ul {
  padding: 0 26.9%;
}
footer ul li {
  display: inline;
  padding: 2.5%;
}
footer img {
  width: 5%;
  margin: 0;
  padding: 0;
}
{% endhighlight %}

Feel free to play around with it or use it as is. Thanks for checking out my work!
