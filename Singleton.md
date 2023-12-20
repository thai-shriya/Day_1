# Singleton Design Pattern

The Singleton Design Pattern is a creational design pattern that ensures a class has only one instance and provides a global point to this instance. It is often used for logging, driver objects, caching, thread pools, database connections, and more. The main idea is to control the instantiation of a class to have only one instance and provide a global point of access to that instance.

Below is the singleton design pattern using double locking - ensuring synchronisation when multiple threads access at the same time.

class Singleton
{
private static volatile Singleton obj = null;
private Singleton() {}
public static Singleton getInstance()
{
if (obj == null)
{
synchronized (Singleton.class)
{
if (obj==null)
obj = new Singleton();
}
}
return obj;
}
}
