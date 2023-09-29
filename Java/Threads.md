
A thread of execution in program (kind of like a virtual CPU)
The [[JDK#JVM|JVM]] allows an application to have multiple threads running concurrently.
Each thread can execute parts of your code in parallel with the main thread.
Each thread has a priority.
Threads with higher priority are executed in preference in comparison to threads with lower priority.

The [[Java]] Virtual Machine continues to execute threads until either of the following occurs
1. The exit method of the class Runtime has been called
2. All user threads have died

When the JVM starts up, there is a thread which calls the main method. This thread is called ``main``

There are two types of threads:
- ``Deamon thread`` is a low priority thread that runs in the background to perform tasks such as garbage collection
- ``User thread`` created threads by default are user threads.


There are two ways of creating threads

The first one using ``Thread``
```java
public class MyThread extends Thread {

}
```

The second one using ``Runnable``
```java
public class MyRunnable implements Runnable {

}
```

But there are some slide differences when instantiating the objects

```java
MyThread thread1 = new MyThread();

MyRunnable runnable1 = new MyRunnable();
Thread thread2 = new Thread(runnable1);
```

Also when creating the class of the new thread you should always override the method run, because its the method that triggers when the threads are started.

```java
public class MyThread extends Thread {
	
	@Override
	public void run() {
		
	}
}
```

#### Some useful methods of threads

```java
MyThread thread2 = new MyThread();
thread2.start(); // To start the thread

thread2.isAlive(); // Check the status of the thread

thread2.getName(); // Displays the name of the thread
thread2.setName("Test Thread"); // this will set the name of the thread

thread2.getPriority(); // Check the current thread priority, by default 5
// Also inherits the priority of its parent 

thread2.setPriority(); // Set a new priority for the thread

Thread.activeCount(); // Checks the amount of active threads

thread2.isDaemon(); // Check's if the thread is a deamon thread or not
thread2.setDaemon(true); // Set's the thread as daemon

```

``join()`` This method tells the main method to not continue the program until this thread finishes its execution
```java
thread2.join();
```

You can pass parameters to this method,  like for example 3000 (milliseconds), so the main will be paused for 3 seconds and then continue the execution.

### Multi threading

Is the process of executing multiple threads simultaneously.
Helps maximize the utilization of CPU.
Threads are independent, they don't affect the execution of other threads.
An exception in one thread will not interrupt other threads, this is useful for serving multiple clients, like multiplayer games or other mutually independent tasks.