---
layout: post
title: Summary of building Github Page with jekyll in Windows7
category: Programming
tag: [ Github, Jekyll, Blog, Windows ]
---

## Summary of building Github Page with jekyll in Windows7

1. Useful Websites:  
		[https://pages.github.com/](https://pages.github.com/)  
		[https://help.github.com/articles/using-jekyll-with-pages/](https://help.github.com/articles/using-jekyll-with-pages/)  
		[http://jekyllrb.com/docs/installation/](http://jekyllrb.com/docs/installation/)  
		[http://jekyll-windows.juthilo.com/](http://jekyll-windows.juthilo.com/) (a guide with steps and details)   
		[http://cn.yizeng.me/2013/05/10/setup-jekyll-on-windows/](http://cn.yizeng.me/2013/05/10/setup-jekyll-on-windows/)   

2. make sure the version of DevKit matches to Ruby's.  
	make sure your directory path does not contain blank space.

3. check the PATH variable.

4. Useful Commands:  
	* [Ruby & DevKit](http://rubyinstaller.org/downloads/)  
	`cd C:\RubyDevKit`  
	`ruby dk.rb init`   
	`ruby dk.rb install`    
	* jekyll  
	`gem update && gem cleanup`  
	`gem install jekyll`  
	`gem uninstall jekyll`  
	`gem update --system`  
	* rouge  
	`gem install rouge`  
	put `highlighter: rouge` into `-config.yml`  
	* pygments (need python)  
	[download](https://pip.pypa.io/en/latest/installing.html) `get-pip.py`   
	`cd C:\pip`  
	`python get-pip.py`  
	`python -m pip install Pygments`  
	put `highlighter: pygments` into `-config.yml`  

5. If you have an SSL problem, copy this file [`cacert.pem`]({{ site.baseurl }}/files/cacert.pem) to your Ruby directory.  
	Then add a variable `SSL_CERT_FILE` in your environment variable, set its value as the location of `cacert.pem`, like `C:\Ruby21-x64\cacert.pem`.  

6. local server:  
	`http://localhost:4000/AAA-Blog/`  

7. No BOM allowed;  
	Set your encoding to UTF-8;  
	put `encoding: utf-8` into `_config.yml`

8. before using local server, change highlighter `pygments` to `rouge`;
	before post a commit to github, change it back.

