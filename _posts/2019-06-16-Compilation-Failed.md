---
layout: post
title: "Compilation Failed"
date: 2019-06-16
---
 <p>
   I am currently working on an astrostatistics project, where I need to transcribing a recently published blaze function fitting code written in R to 
Python. The motivation is that most of the astronomers are big funs of python but do not use much of R. I have never used R before
and I joked to my parents that my current work is like to translate German into Chinese. "But you don't know any German", they commented, unaware of my over exaggeration.  
  </p>  

 <p>
  I had a smooth installation of R and RStudio, but I had problem installing an essential package called "alphahull", which is to
used to compute the alpha-shape and alpha-convex hull of a given sample of points in the plane. To learn more about alpha hull and
alpha shape, you can check <a href="https://cran.r-project.org/web/packages/alphahull/index.html"> here </a>. It is ususally easy
to install a R-package -just type install.packages("pakage_name") in R console. However, when I tried to run nstall.packages("alphahull"),
I found an unexpected compilation error. One of my biggest fears in computer science is that there are so many lower level technicalities I am unfamiliar with. Unlike mathematics,
where we start from learning real numbers, operations, functions so that we can understand college-level real analysis, the education of
computer science tends to start from a very higher level (programming methodologies) to a very lower level (compiler/operating system/....).

  </p>  


<p>
After some trial and fail errors, the following approach worked for me (I used mac):
<br>1. brew install gcc
<br>2. ls /usr/local/Cellar/gcc/version-of-R                
<br>3. sudo vi /Library/Frameworks/R.framework/Resources/etc/Makeconf  
<br>4. In the vi editor, delete the line starting with FlIBS and replace with  FLIBS=-L/usr/local/Cellar/gcc/Version-of-R
</p>  

<p>
My current version of R is 8.3.0 and hope this blog can be helpful for my fellow new R users who encountered compilation error when installing R packages
</p>  
