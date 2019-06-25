<html>
  <head>
    <title>Compilation Failed </title>
    
    <link rel="stylesheet" type="text/css" href="/css/main.css">
  
  </head>


  <body>
    <nav>
<ul>
<li><a href="/">Home</a></li>
<li><a href="/portfolio">Portfolio</a></li>
<li><a href="/cv">CV</a></li>
<li><a href="/blog">Blog</a></li>
</ul>
    </nav>
<div class="container">
<h1>June 25, 2019 : How to call R function within Python</h1>


<div class="post">
 <p>
 Recently, I have been working on transcribing some R projects in Python and the goal is to reproduce the exact same
 result in Python as in R. As a new R user, I just learnt to appreciate R's power to perform statistical analysis over python. Hence it can be beneficial to use some R functions within python. For example, if I want to run a local polynomial regression (loess), there exists a build-in function, loess in R:
 <br>
<code> S_fit <- loess(y ~ x, data = df, degree = 2, span = d,  control = loess.control(surface = "direct"))</code><br>
Loess function in R probably gives you all possible freedom to run loess, such as controlling degree of polynomial, smoothness, and types of approximation. In constrast, in python, there exists a lowess function from the statsmodels package, which is an elder version of loess and doesn't allow users to select degree. Another option is the recently implemented <a href="https://pypi.org/project/loess/"> loess </a> function in Python. The implementation is up to date but the documentation of it can only be acquired if you download its package and check out its examples. Another drawback of using python to run loess (at this stage) is that python doesn't provide the predict function as in R so users have to do interpolation themselves which simply took away the spirit of loess.
 </p>
   
 <p> In my project, I started by using the loess python package and tried to do a linear interpolation myself. The result did not entirely agree with the original R code (though pretty similar), given that I did the interpolation myself. This gave me some trouble since I needed to show my python implementation was correct and could produce the same result. The only way out is if I could call R functions within Python. And yes, this can be done using the rpy2 package and here is how to do this: 
  <br> <code> from rpy2.robjects import r</code>
  <br> <code> import rpy2.robjects as robjects</code>
  <br> <code> x = robjects.FloatVector(list(x))</code>
  <br> <code> y = robjects.FloatVector(list(y))</code>
  <br> <code> loess_fit = r.loess("y ~ x", data=df, degree = 2, span = d, surface = "direct") </code>
  <br> <code> z= robjects.FloatVector(z))</code> <br> 
  
 </p>

 


</div>


</div>
  
  <footer>
   <ul>
   <li><a href="jiguang.li@yale.edu">email</a></li>
   </ul>
  </footer>
  </body>

</html>
