# ServerSideFramework
In web application development while writing the code for backend the programmer needs to keep many things in his mind.For example he has to remember:
1:-the code related to servlet mapping  while writing  the deployment descriptor for his application,  
2:-code for extracting the data when request is recieved by the servlet.
3:-code when request has to be forwarded.
4:- code for file upload etc..
So if the person who is responsible for backend programming is not experienced or  if his coding skills are not up to the mark then there are chances that he 
So, I have created a framework solves these issues.So basically  this framework eases the work of backend programmer.


Requirements:-
1:-Tomcat must be installed in your system.

Steps to use this framework:-
First of all you need to download the zip file from this repository.
then you have to extract the zip folder.
then navigate to the folder and find a file name ServerSideFramework.jar and place this file in the following path:-
path to Tomcat9\webapps\ProjectFolder\WEB-INF\lib
place deplpyment descriptor in WEB-INF folder.
place ServerCOnf.conf file in classes folder.
now your system is ready to use this frmaework.

How to use this framework?

in this framework you can create various services .
sample example of a service:-
package com.thinking.machines.AppliedAnnotation;
import com.thinking.machines.annotations.*;
```
import java.io.*;
import javax.servlet.http.*;

@Path("/Employee")
public class Employee
{
@Path("/Kite") @ResponseType("text/html") 
public void doSomething(HttpServletRequest request,@RequestData("rr")int rollNumber)
{
System.out.println("employee chala");
System.out.println(request);
System.out.println(rollNumber);
}
}
```
