---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

title: "Finn Lestrange's IB Computer Science Portfolio"
layout: splash
author_profile: true

header:
  overlay_color: "#000"
  overlay_filter: "0.4"
  overlay_image: /images/header-1.png
  actions:
    - label: "Download"
      url: "https://github.com/mmistakes/minimal-mistakes/"
  caption: "Photo credit: [**Finn Lestrange**](https://github.com/71xn)"
excerpt: "Hello and welcome to my IB Computer Science Portfolio, using the navigation or the search above you can look through all my work done throughout the IB Computer Science course."
intro: 
  - excerpt: 'Below you will find links to the most important pages on my portfolio.'
feature_row:
  - image_path: /images/code.png
    alt: "code"
    title: "Code"
    excerpt: "This is a link to my **Code** page where there will be subsequent links to my code stored on GitHub or GitLab."
    url: "code"
    btn_label: "Code Page"
    btn_class: "btn--primary"
  - image_path: /images/notes.png
    alt: "notes"
    title: "Notes"
    excerpt: "This is where you will find all of my **Notes** taken throughout the IB computer science course."
    url: "notes"
    btn_label: "Notes Page"
    btn_class: "btn--primary"
  - image_path: /images/lessons.png
    title: "References"
    excerpt: "Here you will find links to useful **References** and additional notes from lessons."
    url: "references"
    btn_label: "References Page"
    btn_class: "btn--primary"

feature_row2:
  - image_path: /profile.jpg
    alt: "profile img"
    title: "About Me"
    excerpt: 'I am 17 years old and I enjoy playing CTFs and cyber sec in general. I really enjoy attacking active directory environments and programming for use in offensive situations.  
    `type="left"`'


---

{% include feature_row id="intro" type="center" %}

{% include feature_row %}

{% include feature_row id="feature_row2" type="left" %}
