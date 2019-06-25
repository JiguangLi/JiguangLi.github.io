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
   
 <p> In my project, I started by using the loess python package and tried to do a linear interpolation myself. The result did not entirely agree with the original R code (though pretty similar), given that I did the interpolation myself. This gave me some trouble since I needed to show my python implementation was correct and could produce the same result. The only way out is if I could call R functions within Python. And yes, I did some basic research and this can actually be done using the rpy2 package as following: 
  <br>
  <br> <code> from rpy2.robjects import r</code>
  <br> <code> import rpy2.robjects as robjects</code>
  <br>
  <br> <code> x = robjects.FloatVector(list(x))</code>
  <br> <code> y = robjects.FloatVector(list(y))</code>
  <br> <code> loess_fit = r.loess("y ~ x", data=df, degree = 2, span = d, surface = "direct") </code>
  <br> <code> z= robjects.FloatVector(z))</code> 
  <br> <code> result= r.predict(loess_fit, z)</code> 
 </p>

 <p>
  In the code above, x,y,z are some python arrays. To call R functions using x,y,and Z, we need to transform these arrays into R vector objects and feed them to the r.loess function. Notice we can also call the predict function in R by using r.predict. While this feels like cheating but the final result does agree with the original code now, so WAH. However, I suspect calling R functions within python can be computationally expensive and there is a danger to incur runtime error. For example, when I tried to call the optim function in R to run Nelder–Mead optimazation, I encountered an unexpected runtime error. I asked this questions on stackoverflow and there are two upvodes now but nobody has answered the question yet (see <a href="https://stackoverflow.com/questions/56738399/how-to-avoid-rruntimeerror-when-calling-r-stats-optim-function-within-python-usi/"> here </a>). If you happen to know how to deal with this error, I would be thrilled to know how.
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
