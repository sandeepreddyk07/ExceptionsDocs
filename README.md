# ExceptionsDocs
Documents and exmples with exceptions

<b>Run Time Stack Mechanism</b>
For every thread jvm will create run time stack each and every method call performed by the thread will be stored in the correcsponding stack.
Each Entry in the stack is called Stack frame or activation record.After completing every method call the corresponding entry from the stack will beremoved.After completing all method call the stack will become empty and the empty stack will be destroyed by jvm before termonating the thread.

<b> Default Exception handling in java</b>
Inside a method if any exception occurs, the method in which it  is raised is responsible to create exception object by including the following information,

1.Name of exception.

2.description of exception.

3.Location at which exception occurs(stack trace).

After creating excepiton object method hand overs that object to the jvm

Jvm will check whether the method contains any exception handling code or not.If the method does not contain exception handling code then jvm terminates that method abnormally and removes the corresponding entry from the stack.

Then Jvm Identifies caller method and checks hether caller method contains any handling code or not .

If the caller Method does not contain handling code , then jvm terminates that caller method also abnormally and removes the corresponding entry from the stack

This process will be continued untill main method and if the main method also does not contain handling code then jvm terminates main method also abnormally and removes corresponding entry from the stack.

Then Jvm hand oversresponsibility of exception handling to default exception handler, which is the part of jvm.
Default Exception handler prints exception information in the following format and terminates program abnormally.

Exception in thread "{threa name}" : {Name of Exception} : {description stack trace}

<b>Exception Hirarchey</b>

Throwable class acts as root for java exception hrarchey, throwable class defines two chid classes
1.Exception.
2.Error

##<b>Exception</b> Most of the times exceptions are caused by our program nd these are <b>recoverable</b> for example if our programming requirement is to read data from remote file located at london , at runtime if remote file is not available then we will get runtime exception saying <b>File Not Found Exception</b> . If file note found exception occurs we can provide local file and continue rest of the program noarmally.

##<b>Error</b> Most of the times errors are not caused by our program and these are due to lack of syatem resources.Errors are non recoverable , for exapmle if outOfMemory Error occurs being a programmer we can not do any thing and the program will be terminated abnoramally.

System admin or server admin is responsible to increase heap memory.

<b>Checked Exceptions vs UnChecked Exceptions</b>

The Exceptions which are checked by compiler for smooth excecution of the program are called checked Exceptions,
Example :FileNotFoundException

In our program if there is achance of rasing checked Exception , then compulsary we should handle that checked Exception ( either by try catch or by throws key word)other wise we will get compile time error.

The exceptions which are not checked by compiler whether the programmer is handling or not , such type of exceptions are called unchecked exceptions.
Example: ArthetmeticException.

NOTE: Whether it is checked or unchecked every exception occurs at runtime only, there is no chance of occuring any exception at compile time.

<b>Run Time Exception and its child classes , error and its child classes are unchecked exceptions , except these remaining are checked.</b>

<b>Fully checked vs partially checked</b>












