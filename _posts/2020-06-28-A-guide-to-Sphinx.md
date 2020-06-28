---
layout: post
title: A guide to Sphinx
tags: [Sphinx, ReStructured-text, Markdown, Technical writing, Documentation, code]
color: brown
author: Shriti
excerpt_separator: <!--more-->
---
<html>
<head>
<style type="text/css">
    .zoomin img {
      height: 200px;
      width: 200px;
      -webkit-transition: all 2s ease;
      -moz-transition: all 2s ease;
      -ms-transition: all 2s ease;
      transition: all 2s ease;
    }
    .zoomin img:hover {
      width: 300px;
      height: 300px;
    }
  </style>
</head>
<body>
<marquee><h2>Unleash the writer in you: Sphinx</h2></marquee>
<br>
    
Looking to combine your love for writing and code?
<br>You're at the right place.
<!--more-->
<br>
Sphinx is a mature tool used for technical documentation. Its what makes your documents look pretty and keeps your users from  getting lost in the maze of thousands of lines and hundreds of pages of code.<br> Keeping it basic, the only assumption I am making here is that you have an internet connection.
Follow these Quick-start instructions for installing, setting up and running Sphinx.
<br><hr>
<h3>How to Install?</h3>
<br>
Skip forward to your O.S and follow the steps to install and set up Sphinx.
Sphinx is written in Python.
<br><br>
<b>Basic Requirements:</b>
<br>
<ul>
    <li> Python (3.6+) </li>
    <li> Pip tool </li>
    </ul>
<br>
<h4>Windows:</h4>
<p>
The most efficient way to work with Sphinx would be to install and run the Windows Subsystem for Linux (WSL).
Refer to the official <a href="https://docs.microsoft.com/en-us/windows/wsl/install-win10">WSL guide</a> for installation instructions.  
After successful installation, run the WSL application and install Python. The Python3 version is preferred.
There are many ways of installing Python on WSL. I am outlining the easiest method here.


{% highlight scss linenos %}
sudo apt-get update && sudo apt-get install python3 python3-pip make git
{% endhighlight %}
</p>
<p>
<br>
But for some reason, if you want to work on your Windows native version, you will have to run command prompt(cmd) or your Power shell in `administrative mode`. This is annoying and makes any errors you make harder to revert. <br>
I am working with Power shell here but you can easily do this on cmd as well.
</p>
<ol>
<li> Installing Python -
<br>
<ul>
<li> Download the <a href = "https://www.python.org/downloads/">python package</a> from  the official website. 
<br> Alternatively, if the above method fails for some reason or if you are feeling a little adventurous, you can install python using `chocolatey`. Chocolatey is     a package manager specially made for Windows which makes it easy to install packages, manage versioning, dependencies and your inventory list.
 <br> Open the windows menu with (Windows + X) and select `Windows PowerShell(Admin)`.
  <p><br>
    Run:<br>
    {% highlight scss linenos %}
        Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString
        ('https:/chocolatey.org/install.ps1'))
        {% endhighlight %}
   <br>
       {% highlight scss linenos %}
        choco install python
        {% endhighlight %}
   <br>

   </li>
 <br>
<li> <p> Installing Pip - 
    <br>
   <i>Pip</i> is a part of the <a href = "https://pypi.org/project/Sphinx/">Python Package Index</a> which houses Sphinx.
Python(3+) versions have pip included as a tool. To check the existence and version of pip,
Run:
 {% highlight scss linenos %}
 python -m pip install -U pip
 pip --version
 {% endhighlight %}
</p></li>
<br>
<li> Install Git for Windows. Follow the instructions <a href = "https://git-scm.com/download/win">here</a>. </li>
<br>
<li> Install Make for Windows and add the following path <code> http://gnuwin32.sourceforge.net/packages/make.htm`
</code> to `PATH` environment variables. </li>
<br>
<li><p>Installing Sphinx - 
<br>
{% highlight scss linenos %}
pip install -U sphinx
{% endhighlight %}
<br><br>
To check whether Sphinx has been installed successfully, <br>
Run:<br>
{% highlight scss linenos %}
sphinx-build --version
{% endhighlight %}
</p></li>

<!--Linux--!>

<h4> Linux </h4>
Linux operating systems usually have Python and Sphinx pre-installed. To check and install Sphinx (if needed),
<ol>
<li> Install the Git tool. Find instructions <a href="https://git-scm.com/">here</a>. </li> <br>
<li> Install GNU Make. Find instructions <a href = "https://www.gnu.org/software/make/">here</a>. </li><br>
<br>
Follow the steps for your Linux O.S:
<p><br><br>
<b> Ubuntu </b>
<br>
{% highlight scss linenos %}
apt-get install python3-sphinx
{% endhighlight %}
<br>
<b> Fedora </b>
<br>
{% highlight scss linenos %}
sudo dnf install python3-sphinx
{% endhighlight %}
<br>
<b> Archlinux </b>
<br>
You can find the official package for Sphinx <a href = "https://www.archlinux.org/packages/community/any/python-sphinx/"> here.</a> <br>Download and install or run the following command.
<br>
{% highlight scss linenos %}
pacman -S python-sphinx 3.1.1-1
{% endhighlight %}
<br>
<b> Anaconda </b>
<br>
{% highlight scss linenos %}
conda install sphinx
{% endhighlight %}
<br>
</p>
</li>
</ol>
<p><br>
Congratulations! You have successfully installed Sphinx :balloon:
</p>
<br>
<p>
Now, navigate to the directory folder where you wish to run Sphinx and run the WSL application by pressing <i>Shift</i> and <i>right click</i> together. Otherwise, run cmd(Admin Mode not needed)/Git Tool(Bash).
</p>
<br>
Run:
<br>
{% highlight scss linenos %}
sphinx-quickstart
{% endhighlight %}
<br><br>
<div class="zoomin">
<img src="assets/img/quickstart.png" width="200px" alt="sphinx-quickstart">
</div>
<br><br>
This will give you these newly furbished files:
<br>
<ul>
<li> Makefile: The source and build directories are defined here, originally set to point to the Source and Build folders in the Sphinx file. If you need to change the path to point to another folder, you can make the changes here.
The Makefile also allows you to build your document with the help of various supporter builder (html, latex etc.) </li>
<li> Make Windows Batch file: Unless you know what you are doing, leave this alone. </li>
<li> Source folder:
    <ol>
    <li> <i>_static</i> file: Holds the static files Sphinx uses to host your pages. </li>
    <li> <i>_templates</i> file: Holds the various templates you can implement for your pages. </li>
    <li> <i>config.py</i> file : Holds configuration settings; including an option to change the theme. </li>
    <li> <i>index.rst</i>: A list of contents listed under the `..  toctree::`, which you will need to amend every time you add a new file to your Sphinx source folder. </li>
    </ol>
<li> Build folder (empty) </li>
</ul>
<br>
<hr>
Now that we have the guns and the ammunition, lets fire off a new documentation site.<br>
I am using html build here. You can alternatively use latex, linkcheck etc.<br>
<i>make html</i> builds your file written in Markdown, HTML and ReStructured text into a static site, allowing you to view it locally before committing to the changes.<br><br>
Run:
<br>
{% highlight scss linenos %}
make html
{% endhighlight %}
<br><br>
<div class="zoomin">
<img src="assets/img/make.png" width="200px" alt="make html">
</div>

<br>

Go to your <i>build</i> folder. You will find two folders, <i>doctree</i> and <i>html</i>, waiting for you. Open the </i>html</i> folder.
<br>
<div class="zoomin">
<img src="assets/img/build.png" width="200px" alt="build file">
</div>
<br>

Open the index.html file in the browser of your choice.
<br>
<div class="zoomin">
<img src="assets/img/index.png" width="200px" alt="index site view">
</div>
<br> <br>

You can now populate your source folder with more files. You can use any editor, even notepad, to play around with your .rst files. Make sure to run `make html` every time you want to build and see any changes locally (on your system).
<br> <br>

<h3>Tips</h3>
<br><p>
Sphinx doesn't inherently use any customization language. This is because it is mainly used for structuring and mature documentation. This does not mean that you cannot style your document by adding colors, highlights etc.
Adding CSS or Java script(JS) files to Sphinx is very much possible.
In case you need to need to do some styling at a minor level, you can accomplish this even without going through the bother of setting up a separate CSS/JS file by simply adding roles to your markdown file.
Roles act like <i><span></i> html tags.
In this short tutorial, I have used roles to add colors to the text. This might also give you an insight to the entire building process.
</p>
<br>
<br>
<video width="400" height="280" controls>
  <source src="assets/colored_text".mp4" type="video/mp4">
  <source src="movie.ogg" type="video/ogg">
  Your browser does not support the video tag.
</video>
<br>
As an alternative, you can simply create/link a CSS or JS file to your `.rst` file and go crazy on the styling.
<br><br>
If you are not familiar with Markdown or ReStructured language, consider the following references as your bible:
    <ul>
    <li> <a href = "https://docutils.sourceforge.io/docs/ref/rst/directives.html#raw-data-pass-through"> reST Primer</a> </li>
    <li> <a href = "https://thomas-cokelaer.info/tutorials/sphinx/rest_syntax.html"> reST and Sphinx Cheat Sheet</a> </li>
    <li> <a href = "https://guides.github.com/features/mastering-markdown/"> Github Markdown Primer </a> </li>
    <li> <a href = "https://rmarkdown.rstudio.com/authoring_basics.html"> Markdown Basics ~ Rstudio </a></li>
    </ul>

</body>
</html>
