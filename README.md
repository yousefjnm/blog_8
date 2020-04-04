# blog_8

How to add a python library package to AWS lambda to be able to use it there?

Following my methof to explain different topics, I will use the library "reportlap" as an example in the explaination.

Assuming that you use "pip install <package name>" to install Python packages, you will need to run "pip install reportlab"

This will istall the reprtlab package and all its depences along with it and you can find that in the lib directory where Python exists in your system. 

From lib directory, look for reportlab package and all other packages that were installed along with it like Pillow and numpy and some more ppackages. You will copy all of them and put them in a separate directory/folder and name it as "python". then zip that python folder with all those packages inside.


Second step will be to go to Lambda in AWS and then go to "layers" in there, click "create layer", upload the zipped file to there, name the layer with a name that will help you know that this is reportlab, select the "Compatible runtimes" and that would be whatever languages that library is compatible with and you could use it with(up to five chioces).

Uploading the zip file directly to there is one way but the other way, which you need to do if the zipped file size is greater than 10MB, is to first upload the file to S3 and then add it's S3 URL and put in there instead.

Last step, click "create layer", wait for a few seconds while AWS processes it and now you're all set!!!!!

To test got to your lambda function, go to "layers" in the "designer" part and then add that new layer(you have up to five layers to add for each Lambda function). type "import reportlab" in the function code and save it. click test, if you get no error that means you were able to add the package successfully, Congrats!!



Note: Most Python modules are platform-independent, but some modules are compiled against specific operating system environments. AWS Lambda runs under a Linux environment. If you are installing modules with pip for deployment, it's a best practice to build the .zip file in a Linux environment to be sure that dependencies are included for the correct platform.
