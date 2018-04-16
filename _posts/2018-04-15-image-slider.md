---
layout: post
title: 'Image slider in JavaScript'
date: 2018-04-16
excerpt: "Image slider for a travel blog"
tags: [sample post, code, highlighting]
comments: true
---

Here is an image slider that I built in JavaScript. The slider features 3 photos at a time and functioning
previous and next buttons that allow the user to toggle through an entire photo album. It also cycles back
through once you reach the end so the user can enjoy a seamless photo viewing experience. Enjoy!

## HTML

#### The photos are organized in divs of 3 photos each. So the JavaScript targets these divs instead of the images themselves.

{% highlight html %}
{% raw %}
<section class="container">
    <div class="slider-outer">
      <img src="img/chevron-left.png" class="prev" alt="Prev"/>
        <div class="slider-inner">
          <div class="active">
            <img src="img/strait-of-gibraltar.jpg" alt="selfie on ferry crossing the strait of gibraltar"/>
            <img src="img/oporto-puente.jpg" alt="selfie on bridge crossing the Douro river"/>
            <img src="img/libertad.jpg" alt="my sailboat"/>
          </div>
          <div>
            <img src="img/malaga-fuente.jpg" alt=""/>
            <img src="img/fifth-birthday.png" alt=""/>
            <img src="img/snowboarding-lapinilla.jpg" alt=""/>
          </div>
          <div>
            <img src="img/svqbbq-2015.jpg" alt=""/>
            <img src="img/the-climb-mbt.jpg" alt=""/>
            <img src="img/urban-monkey-mbt.jpg" alt=""/>
          </div>
        </div>
      <img src="img/chevron-right.png" class="next" alt="Next"/>
    </div>
  </section>
{% endraw %}
{% endhighlight %}

## CSS

#### Important things to note:
  * display: none; in the .inner-slider div rule makes the inactive divs not show up.
  * display: inline-block; in the .inner-slider div.active rule then allows only the div with the active class to show up at any one time.

{% highlight css %}
.container {
  background: rgba(0,0,0,0.7);
  overflow: auto;
}
.slider-outer {
  position: relative;
  margin: 0 auto;
  padding: 3%;
  width: 80%;
  height: auto;
}
.slider-inner {
  background: #000;
  position: relative;
  overflow: hidden;
  float: left;
  padding: 20px 0;
  width: 100%;
  height: auto;
}
.slider-inner img {
  margin-left: 3%;
  width: 30%;
  height: auto;
}
.slider-inner img:first-child {
  margin: 0;
}
<b>.slider-inner div {
  display: none;
}
.slider-inner div.active {
  display: inline-block;
}</b>
.slider-outer img {
  width: 25%;
  height: auto;
  border-radius: 5px;
  box-shadow: 4px 4px 20px;
}
.slider-outer .prev,
.slider-outer .next {
  background-color: #f5f5f5;
  width: 5%;
  height: auto;
  float: left;
  cursor: pointer;
  z-index: 200;
}
.slider-outer .prev {
  position: absolute;
  left: -5%;
}
.slider-outer .next {
  position: absolute;
  right: -5%;
}
{% endhighlight %}

## JavaScript/jquery

{% highlight JavaScript %}
$(document).ready(function(){
  var startDiv = $('.slider-inner div:first-child')
  var lastDiv = $('.slider-inner div:last-child')
  var currentDiv = startDiv;
  var count = 1;
  var totalDivs = $('.slider-inner > div').length;

  $('.next').on('click', function(){
    if (count == totalDivs) {
      currentDiv.hide()
      currentDiv = startDiv.show()
      count = 1
    } else {
      currentDiv.hide()
      currentDiv = currentDiv.next().show()
      count ++
    }
  });

  $('.prev').on('click', function() {
    if (count == 1) {
      currentDiv.hide()
      currentDiv = lastDiv.show()
      count = totalDivs
    } else {
      currentDiv.hide()
      currentDiv = currentDiv.prev().show();
      count--
    }
  });
});
{% endhighlight %}

Feel free to play around with it or use it as is. Thanks for checking out my work!
