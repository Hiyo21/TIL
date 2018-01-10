# JVM Structure

## 1. ClassFile

   .java==Java Compiler==> .class


## 2. Class Loader

   What's class loading? Read .class files, then load them onto JVM memory. How?
    - Analyze .class files by reflection and find out what kind of methods and variables are in there.
    - categorize them and load them onto JVM Area where they fit the best.
    - As the class is being run, loaded classes are copied onto heap memory area.
    - System resources are used to run classes.

   > dynamic loading = load classes as the program is being run. There are 2 types:
   >  - Load time dynamic loading : as the class is loaded
   >  - Runtime dynamic loading : even when the program is running
 

## 3. Runtime Data Area

  * Method Area
  
    area where loaded classes are stored with metadata (info about methods and variables) 
  
  * Stack Area
  
    area where method call data is stored
    LIFO
   
  * Heap Area
  
    area where objects are created and stored
    garbage collected
    able to tune 
  
  * PC Register Area
  
    area where next operation address is stored.
    
  * Native Method Area
  
    where native OS, system, and resources are accessed
 
  * Garbage Collection
   
    - Largely divided into 3 areas : Young, Old, Permanent
    - Young area divided into 3 : Eden, Survivor1, Survivor2
    - Young : where freshly created objects are stored.
    - Old : more frequently used data are moved to Old area.
    - Permanent : data about class is stored.
  
 # String Class
   ## StringBuilder vs StringBuffer
     - StringBuffer is synchronized, StringBuilder is not.
     
