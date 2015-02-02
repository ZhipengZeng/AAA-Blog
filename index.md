---
layout: default
title: my github blog
---
##{{ page.title }}  
the latest note  
- {% for post in site.post %}  
- {{ post.date | date_to_string }} [{{ post.title }}]({{ site.baseurl }}{{ post.url }}  
- {% endfor %}
