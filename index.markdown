---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

title: "Finn Lestrange's IB Portfolio"
layout: splash
author_profile: true

header:
  overlay_color: "#000"
  overlay_filter: "0.4"
  overlay_image: /images/header-images/header-1.png
  caption: "Photo credit: [**Finn Lestrange**](https://github.com/71xn)"
excerpt: "Hello and welcome to my IB Portfolio, using the navigation or the search above you can look through all my work done throughout the IB Diploma."
intro: 
  - excerpt: 'Below you will find links to the most important pages on my portfolio.'
feature_row:
  - image_path: /images/header-images/code.png
    alt: "code"
    title: "Computer Science"
    excerpt: "This is a link to my Computer Science page where there will be subsequent links to my work and notes."
    url: "compsci"
    btn_label: "Computer Science"
    btn_class: "btn--primary"
  - image_path: /images/header-images/personal.png
    alt: "notes"
    title: "Personal Work"
    excerpt: "Here is a link to my personal work."
    url: "https://71xn.github.io"
    btn_label: "71xn.github.io"
    btn_class: "btn--primary"
  - image_path: /images/header-images/physics.jpg
    title: "Physics"
    excerpt: "Here you will find all of Physics HL work."
    url: "physics"
    btn_label: "Physics Page"
    btn_class: "btn--primary"

feature_row2:
  - image_path: /images/me.jpg
    alt: "profile img"
    title: "About Me"
    excerpt: "Hello, I'm Finn, I am 17 years old and I enjoy playing [CTFs](https://ctftime.org) and [Hack The Box](https://hackthebox.eu) and programming for use in offensive situations. I hope this portfolio is some use to you and any suggestions or queries please contect me via the email link [here](mailto:flestrange@isa.aberdeen.sch.uk)."
---

{% include feature_row id="intro" type="center" %}

{% include feature_row %}

{% include feature_row id="feature_row2" type="left" %}