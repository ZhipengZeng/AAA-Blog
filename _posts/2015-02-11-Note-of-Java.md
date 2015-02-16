---
layout: post
title: Note of Java 
category: Programming
tag: [ Java,  Note ]
---

## Something in Java

1. (11/02/2015) Could not center JLabel in JPanel's BorderLayout?  
	**Solution:**
{% highlight java %}
JPanel myPanel = new JPanel(new BorderLayout());
JLabel myLabel = new JLabel("make me center");
myLabel.setHorizontalAlignment(JLabel.CENTER);
myPanel.add(label, BorderLayout.CENTER);
{% endhighlight %}
