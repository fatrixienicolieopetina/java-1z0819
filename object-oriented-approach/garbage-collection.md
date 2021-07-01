# Garbage Collection
### 📌 Notes
1. Managing memory explicitly is tedious and error prone. 
2. The Java Platform allows you to create as many objects as you like (as to what the system can handle) and there is no need to worry of destroying them.
3. The Java Runtime Environment (JRE) deletes objects when it determines that they are no longer being used -> **Garbage Collection**. 
4. An object is eligible for garbage collection when there are no more references to the object.
5. Variable references are usually dropped when they get out of scope.
6. An object can be explicitly dropped by setting its value to `null`.
7. A program can have multiple references to the same object, so all of them must first be dropped before the object is eligible for garbage collection.
8. The JRE has a garbage collector that periodically frees memory used by objects that are no longer referenced. The garbage collector does its job automatically when it determines that the time is right.
