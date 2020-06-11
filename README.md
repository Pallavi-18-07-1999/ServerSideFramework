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
place ServerConf.conf file in classes folder.
now your system is ready to use this frmaework.

How to use this framework?

While writing the code for services you can use various annotations like :-


Path Annotation

```
package com.thinking.machines.AppliedAnnotation;
import com.thinking.machines.annotations.*;

import java.io.*;
import javax.servlet.http.*;

@Path("/Employee")
public class Employee
{
@Path("/Kite") @ResponseType("text/html") 
public void doSomething(@RequestData("id")int employeeId)
{
System.out.println(employeeId);
}
}
```
It is mandatory to apply Path Annotation on every class and method.Also you have to include /service in every url-pattern.
So if the url-pattern is /service/Employee/Kite then doSomething method will be called.


RequestData Annotation:-

you have to apply RequestData annotation on those methods whose parameters have primitive data types,their wrappers and String type.

Forward Annotation:-
if you wanrt to forward the request to any other service or jsp/html file then you have to apply this annotaion.

```
package com.thinking.machines.AppliedAnnotation;
import com.thinking.machines.annotations.*;
import java.io.*;
import javax.servlet.http.*;

@Path("/Student")
public class Student
{
@Path("/Kite") @ResponseType("text/html") @Forward("/service/Employee/Kite")
public void doSomething(HttpServletRequest request,@RequestData("rr")int rollNumber)
{
System.out.println(request);
System.out.println(rollNumber);
}
}
```
Secured Annotation 
if you want to create a service that should onle be accessed when the user has provided his credentials then you can use secured annotation.

``
package com.thinking.machines.AppliedAnnotation;
import com.thinking.machines.annotations.*;
import java.io.*;
import javax.servlet.http.*;

@Path("/Student")
public class Student
{
@Path("/Kite") @ResponseType("text/html") @Secured("com.thinking.machines.implementations.Login")
public void doSomething(HttpServletRequest request,@RequestData("rr")int rollNumber)
{
System.out.println(request);
System.out.println(rollNumber);
}
}
```

File Upload 
if you want to upload a file then you have to use UploadAnnotation.


viewing pdf file:-

if you want to have a look on the services you have creates 











