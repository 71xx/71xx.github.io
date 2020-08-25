---
layout: single
author_profile: true
permalink: /code/
toc: true
title: Code Repo
toc_label: "Contents"
toc_icon: "fab fa-fw fa-th-list"
---

## Code Page Samples

Currently this page is just showing samples of what my code page will look like but eventually it will have a gigantic table of contents and external links to my code on github / gitlab etc.

### GitHub Gist Example

{% gist 00296db9fe8d812cfb961e8031029ce6 %}

### Java

{% highlight java linenos %}
public class Main {
    public static void main(String[] args) {
        System.out.println("This will be printed");
    {
}
{% endhighlight %}


### Python

{% highlight python linenos%}
print("Hello World")
{% endhighlight %}


### Ruby

{% highlight ruby linenos%}
puts 'Hello World!'
{% endhighlight %}


### Rust

{% highlight rust linenos%}
fn main() {
    println!("Hello, world!");
}
{% endhighlight %}


### C++

{% highlight c++ linenos%}
#include <iostream>

int main()
{
    std::cout << "Hello, world!\n";
    return 0;
}
{% endhighlight %}