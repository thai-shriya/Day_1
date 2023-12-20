# Main differences between hashmap and hash table

Synchronization:

HashMap: It is not synchronized, meaning it is not thread-safe. Multiple threads can manipulate a HashMap simultaneously, and external synchronization is required if used in a concurrent environment.
Hashtable: It is synchronized, which means it is thread-safe. All of its methods are synchronized, making it safe to use in a multi-threaded environment. However, this comes at the cost of reduced performance compared to HashMap.

Null values:

HashMap: Allows one key to be null and multiple values to be null.
Hashtable: Neither keys nor values can be null. If you try to store a null key or value, a NullPointerException will be thrown.
