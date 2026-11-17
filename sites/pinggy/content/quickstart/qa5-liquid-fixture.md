---
title: "QA5 liquid fixture"
description: "Disposable Liquid fixture for byte checks."
date: 2026-11-18T10:00:00+05:30
draft: false
---

Paragraph before the include. QA5

{% include cta-box.html
  headline="Want analytics?"
  link="/most-accurate-web-analytics"
%}

Paragraph after the include with \{\{ site.title }} and a filter \{\{ page.date | date: "%Y" }}. QA5

{% raw %}
Literal {{ not_a_variable }} inside raw.
{% endraw %}

{% highlight ruby %}
puts "hi"
{% endhighlight %}

Closing paragraph.
