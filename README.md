# blog_8

How to add a python library package to AWS lambda to be able to use it there?

Following my methof to explain different topics, I will use the library "reportlap" as an example in the explaination.

Assuming that you use "pip install <package name>" to install Python packages, you will need to run "pip install reportlab"

This will istall the reprtlab package and all its depences along with it and you can find that in the lib directory where Python exists in your system. 

From lib directory, look for reportlab package and all other packages that were installed along with it like Pillow and numpy and some more ppackages. You will copy all of them and put them in a separate directory/folder and name it as "python". then zip that python folder willl all those packages inside.

Now go to Lambda in AWS











Note: Most Python modules are platform-independent, but some modules are compiled against specific operating system environments. AWS Lambda runs under a Linux environment. If you are installing modules with pip for deployment, it's a best practice to build the .zip file in a Linux environment to be sure that dependencies are included for the correct platform.
